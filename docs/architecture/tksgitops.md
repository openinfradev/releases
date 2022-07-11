# GitOps pipeline

# 문서의 목적

본 문서는 SKT Enterprise Kubernetes Solution이 제공하는 CustomCluster에 대한 이해를 목적으로 한다.

# 배경지식 : Decapod

SKT는 GitOps pipeline으로 Decapod(Declarative Application Orchestration & Delivery)라는 기술을 사용한다.
**Decapod는 Kubernetes에 다양한 Application으로 구성된 Application Group을 다양한 환경에 배포하기 위해 SKT가 개발한 GtiOps Pipeline 이다.**

## Problem
Application Group을 다양한 환경에 반복적으로 배포하기 위해서는 아래와 같은 어려움이 있다.

- **Massive Documentation**   
    Kubernetes는 단일 Application을 배포하고 서비스하기 위해, 복수의 선언문(yaml file)이 필요하다. 따라서 단일 Application을 위한 설정 또한 복수의 yaml file들의 변경을 통해 실행 된다. 이런 복잡성을 해결하기 위해 Helm이라는 기술이 보급되었다. 하지만 우리가 사용하는 대분의 서비스는 복수의 Application 들로 구성된 Application Group 이다. 따라서 Application Group의 구성관리 및 설정(Documentation)을 간단하게 할 수 있는 툴이 필요하다.
- **Complex Deployment**   
    복수의 Application로 구성된 Application Group을 배포할 때, 각 Application간 Dependency를 고려해야 한다. 즉 Application Deployment간 flow control이 필요하며, 때로는 Deployment 시점에 생성되는 value의 관리가 필요하다.
## Solution : Decapod   
Decapod는 언급된 Massive Documentation과 Complex Deployment에 대한 SKT의 Solution이다.
![https://raw.githubusercontent.com/openinfradev/decapod-docs/main/docs/assets/decapod-flow.svg](https://raw.githubusercontent.com/openinfradev/decapod-docs/main/docs/assets/decapod-flow.svg)

Decapod는 구성 요소에 대한 설명이다.

- **Decapod-base-yaml**   
    SKT가 정의한 Application Group의 구성에 대한 단일 yaml file이다.  Git repo 형태로 제공된다. 
- **Decapod-site**   
    SKT가 개발한 SW에 의해 Application Group에 적용될 구성/설정이 완료된 단일 yaml file 이다. Git repo의 형태로 제공된다. 
- **Decapod-manifests**   
    SKT가 개발한 SW에 의해 Decapod-base-yaml(구성)에 Decapod-site(구성/설정)를 해석하여 만드 배포가능한 표준 Kubernetes Resource(yaml files)이다. Git repo의 형태로 제공된다.
- **Agro Worflow**    
    Complex Deployment 문제를 해결하기 위해, 도입한 Workflow Engine으로 SKT가 Application Group별로 개발한 Workflow가 실행된다. Argo CD의 Deployment 순서를 제어한다.   
- **Argo CD**   
    GitOps 툴로 decapod-manifests에 저장된 yaml file들을 원하는 Target (Cluster or Public Clutser)에 배포하는 툴이다
# SKT Enterprise Kubernetes Solution GitOps pipeline
SKT Enterprise Kubernetes Solution의 GitOps pipleline은 Decapod 이다. Decapod는 Kubernetes Cluster도 배포 관리 할 수 있다. 이는 Cluster API라는 기술을 활용 했기 때문이다.
Cluster API는 Kubernetes Cluster와 Cluster를 구성한는 Server / OS 그리고 Network을 Kubernetes Resource로 관리한다. 따라서 Decapod가 Application Group를 관리하는 방법과 동일 하게 Kubernetes Cluster 자체도 관리 할 수 있다.
> Cluster API is a Kubernetes sub-project focused on providing declarative APIs and tooling to simplify provisioning, upgrading, and operating multiple Kubernetes clusters.
## 제공되는 Repo
SKT Enterprise Kubernetes Solution의 고객에게는 GitOps 가준, 아래 3개의 Repo를 제공한다.
[참고] 고객은 Github Organization Account를 사전에 제공해야 한다.
decapod-base-yaml과 tks-custom-base-yaml 를 기반으로 최종적으로 고객의 custom cluster tempate인 {contact} 를 생성한다.

**고객은 site 변경을 통해 cluster를 customization 할 수 있다.**

ovlery란 단순이 변경이나 치환이 아니라, 추가/삭제/변경 이 모두 가능하다는 의미다.

```
+----------------------------------+              +-----------------------+
|            base-yaml             |              |                       |
|   +--------------------------+   |              |      {contact id}     |
|   |      tks-custom-yaml     |   |         \    |                       |
|   +--------------------------+   |          \   |                       |
|            Overlay  +            | -----------  |     CustomCluster     |
|   +--------------------------+   |          /   |        Editable       |
|   |    decapod-base-yaml     |   |         /    |                       |
|   +--------------------------+   |              |                       |
+----------------------------------+              +-----------------------+
```
- decapod-base-yaml   
    SKT가 Open Source로 관리하는 Application Group의 이다. 고객의 상황에 맞는 Release를 선택한다. 
    ```bash
    github.com/openinfradev/decapod-base-yaml
    └──  decapod-base-yaml           
         └── lma
         |   └── base
         |   |   ├── kustomization.yaml
         |   |   ├── resources.yaml       # default 구성
         |   |   └── site-values.yaml     # 구성에 대한 overlay
         |   └── image
         |       └── image-values.yaml 
         └── service-mesh
             └── base
             |   ├── kustomization.yaml
             |   ├── resources.yaml       # default 구성
             |   └── site-values.yaml     # 구성에 대한 overlay
             └── image
                 └── image-values.yaml
    ```

- tks-custom-base-yaml   
    SKT가 Open Source로 관리하는 Application Group 중 Kubernetes cluster에 관한 부분이다. Decapod는 LMA와 같은 Kubernetes위에 올라가는 서비스와 Kubernetes를 같은 체계로 관리한다. 고객의 상황에 맞는 Release를 선택한다. 
    ```bash
    github.com/openinfradev/tks-clustom-base-yaml
    └──  tks-base-yaml           
         └── tks-cluster-aws
             └── base
                 ├── kustomization.yaml
                 ├── resources.yaml       # default 구성
                 └── site-values.yaml     # 구성에 대한 overlay
    ```
## 생성되는 Repo   
SKT가 Open source로 제공하는 base-yaml를 기반으로 TKS가 고객(사용자)의 Git organization에 자동으로 생성하는 Repo 다.

- {contract id} 
    고객이 사용할 최종 구성/설정이다. 고객에게 제공되는 customized decapod-site 로 Custom Cluster Template 역활을 한다.
    **고객은 site 변경을 통해 cluster를 customization 할 수 있다.** 
    ```bash
    github.com/{organization name}
    └── {contract id}               
        ├── .github
        │   └── workflows
        │       ├── merge_main.yml
        │       ├── render-cd.sh
        │       └── render.sh
        └── tmeplate-std
            ├── lma
            │   ├── kustomization.yaml│      
            |   └── site-values.yaml         ## 고객환경에 최적확된 구성 overlay
            ├── service-mesh
            │   ├── kustomization.yaml
            │   └── site-values.yaml         ## 고객환경에 최적확된 구성 overlay
            └── tks-cluster-aws   
                ├── kustomization.yaml        
                └── site-values.yaml         ## 고객환경에 최적확된 구성 overlay
    ```


TKS Service API 호출 (e.g. by CLI)를 통해 TKS Cluster를 생성할 수 있다. Decapod는 GitOps 툴이므로, TKS Cluster 생성/관리를 위해 각 Cluster별로 site와 manifest repo를 생성한다.

- {cluster id} 
    Cluster별 생성되는 site다.
    site-{contact id}의 복사본으로 site별로 관리되야 할 구성/설정이 적용되어 있다.
    ```bash
    github.com/{organization name}
    └── {cluster id}                       # Cluster별 설정값
        ├── META                           # Cluster에 대한 설명 metadata
        ├── .github
        │   └── workflows
        │       ├── merge_main.yml
        │       ├── render-cd.sh
        │       └── render.sh
        └── {cluster id}
            ├── lma
            │   ├── kustomization.yaml
            │   └── site-values.yaml
            ├── service-mesh
            │   ├── kustomization.yaml
            │   └── site-values.yaml
            └── tks-cluster-aws
               ├── kustomization.yaml
               └── site-values.yaml
    ```
    
- {cluster id}-manifests
    cluster별로 생성되는 manifest다.
    cluster별로 다른 구성/설정을 GitOps로 관리하기 위해 별도로 생성된다.
    ```bash
    github.com/{organization name}
    └── {contract id}-manifiest            # Cluster별 설치되는 Manfiests
        └── {cluster id}
            ├── lma
            ├── service-mesh
            └── tks-cluster-aws
    ```
    

# CustomCluster
{contract id} repo의 각 Application Group (lma, service-mesh,tks-cluster-aws)의 site-values.yaml file의 변경을 통해 Customization 가능하다.
