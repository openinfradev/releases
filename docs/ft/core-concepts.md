# Core Concepts

kubernetes 및 gitOps 개념에 익숙하다고 가정해 보겠습니다. 다음은 SKT Enterprise Container Solution 에서 사용하는 개념들입니다.


- **Project**   
    SKT Enterprise Container Solution에서 사용하는 최상위 워크스페이스의 개념입니다. 각 클러스터가 사용하는 각종 공통의 설정 및 서비스 권한등을 관리하는 논리적인 그룹입니다.   
- **Stack**   
    Kubernetes 클러스터와 서비스의 조합입니다. 클러스터와 TKS가 제공하는 built-in 서비스들을 하나로 묶은 Template 패키지입니다.
- **Cluster**   
    TKS 가 제공하는 kubernetes 클러스터입니다. kubernetes cluster-api 를 사용하여 gitOps 로 관리되는 kubernetes 클러스터를 설치/제공합니다.
- **Template**   
    Kubernetes 클러스터, 그 위에 설치되는 모든 서비스는 내부적으로 gitOps 방식으로 관리됩니다. gitOps 에서 사용하는 Kubernetes 명세 패키지로서 Kubernetes 클러스터와 pre-defined 상태의 서비스들을 포함합니다.
- **Service**   
    TKS 가 제공하는 built-in 소프트웨어입니다. Free-Trial 서비스에서는 LMA, ServiceMesh 서비스를 제공합니다.
- **AppServing**   
    TKS 가 제공하는 Continuous Deployment 솔루션입니다. spring boot 의 결과물만으로 손쉽게 kubernetes 클러스터에 배포/관리 할 수 있습니다.   
    > [App Serving 설명](../architecture/appserving.md)   
- **Infra Provider**   
  Free-Trial 버전에서는 AWS 인프라 프로바이더만 지원합니다. 정식 버전에서는 BYOH, BYOK 등 다양한 on-prem 프로바이더를 지원합니다.
