
# TKS(TACO Kubernetes Service)

SK테레콤은 가상화를 4G/5G에 선도적으로 적용해 왔고, 이를 위해 OpenStack과 같이 복잡한 Service를 효율적으로 관리하는 기술을 개발해 왔다.
이러한 노력에 대한 결과물은 여러 사람들이 널리 이롭게 사용하도록 Open Source로 공개해 왔다.
가장 대표적인 Open Source는 Decapod로 Decapod는 Open Source로 구성된 복잡한 Service를 Containerization를 통해 선언적으로 관리하는 GitOps CD pipeline이다.

TKS는 Decapod를 Core기술로, Kubernetes Cluster와 Kubernetes를 운영하기 위한 Add-on (CNI, CSI, Ingress Controller등)과 필수 서비스들 (Monitoring, Service Mesh)를 All-in-One으로 제공하는 통합 컨테이너 관리 플랫폼이다.

> [What is a container ? - Docker](https://www.docker.com/resources/what-container/)
> [What is a CaaS ? - RedHat](https://www.redhat.com/en/topics/cloud-computing/what-is-caas)

TKS의 주요 특징은 다음과 같다.
- Hybrid Cloud 지원
- All-in-One Package
- CaaS (Container as a Service)

![TKS](https://github.com/openinfradev/tks-docs/blob/main/docs/assets/images/tksre21arch.png?raw=true)

WikiPage: https://openinfradev.github.io/releases/

