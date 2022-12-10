# About Free-Trial Service

SKT Enterprise Container Solution은 그 동안 SKT가 공개해 왔던 Open Source를 활용하여 구성된 Production level의 Kubernetes 배포관리 Solution 입니다. SKT Enterprise Container Solution 의 많은 Feature 중 대표적인 기능을 UI 로 구현하여, 누구나 쉽게 웹 UI 를 통해 SKT Enterprise Container Solution 서비스를 경험해 볼 수 있도록 FreeTrial 서비스를 출시 하였습니다.

저희는 kubernetes를 처음 도입하려는 고객이 겪는 대표적인 어려움 몇 가지에 집중 하였습니다.

- **구축**    
  첫째, kubernetes 도입의 시작은 kubernetes 클러스터의 설치입니다. kubernetes를 설치 할 머신 준비 부터 방화벽, 소프트웨어까지, 고려해야 하는 많은 선택지가 있으며 이는 높은 전문성을 요구하는 일입니다. 전문 kubernetes 엔지니어 없이 실제로 서비스 운영이 가능한 수준의 클러스터를 구축하는 것은 분명 쉽지 않은 일입니다.
- **운영**      
  둘째, 구축한 클러스터가 유효한지, 운영을 위한 시스템/어플리케이션 레벨의 모니터링 솔루션을 구성해야 합니다. 시중에 다양한 무료/상용 소프트웨어가 있으나 사용자의 입맛에 맞게 세팅/구축하기 위해서는 역시 적지 않은 비용과 노력이 필요합니다. 
- **사용**        
  셋째, 클러스터 설치 및 시스템 운영이 가능한 수준의 모니터링 시스템을 구축했다고 하더라도 실제로 사용자 어플리케이션을 배포/관리하는데는 또 다른 높은 허들이 존재합니다. kubernetes 에 대한 이해가 선행되어야 하기에 어플리케이션을 클러스터에 배포하는데 많은 어려움을 겪을 수 밖에 없고, kubernetes 의 다양한 장점을 활용하려면 높은 수준의 전문성이 필요합니다.


SKT Enterprise Container Solution은 이 모든 허들을 최대한 낮추기 위해 노력 하였습니다. kubernetes 클러스터를 구축하고, 운영하고, 사용할 수 있는 "가장 쉬운 방법"이 무엇일까 끊임없이 고민하였습니다. 

여기 그에 대한 저희의 답을 TKS Console Free-Trial 서비스를 통해 공유합니다.


- **TKS Console 은 최소 선택, 최적의 결과물을 지향합니다.**    
  사용자의 선택지를 최소화하여 반드시 필요한 입력만으로 production ready 수준의 안정적이고 파워풀한 kubernetes 클러스터를 잘 구성된 소프트웨어와 **함께 제공**합니다. 내부적으로 완전히 검증된 상태의 클러스터와 서비스를 클릭 한번으로 동시에 제공함으로써 kubernetes 를 잘 모르는 사용자라도 쉽게 kubernetes 클러스터를 접할 수 있게 하였습니다. 뿐만아니라 이렇게 제공된 클러스터와 서비스는 IaC(Infrastructure as a code)" 수준을 넘어 100% gitOps 방식으로 완전히 추상화되어 관리되기 때문에 투명하고 신속한 인프라 관리가 가능해집니다.

- **TKS Console 은 미리 검증되고 설정된 다양한 개발/운영 도구를 기본 제공합니다.**    
  클러스터에 포함된 pre built-in 서비스는 kubernetes 클러스터와의 종속성까지 검증된 상태로 제공이 되므로 아무런 사전 작업 없이 그 즉시 사용 가능합니다. 운영을 위한 다양한 대시보드, 로그 검색 시스템, 멀티 클러스터 모니터링 시스템까지 Logging, Monitoring, Alerting 기능을 하나의 패키지로 통합하였습니다. 또한 MSA 개발을 위한 사용자들을 위해 istio와 이를 모니터링 할 수 있는 자체 개발 통합 모니터링 도구를 기본으로 제공합니다.

- **TKS Console 은 사용자 어플리케이션을 쉽게 클러스터에 배포합니다.**    
  kubernetes 에 익숙하지 않은 사용자라도 어플리케이션을 손쉽게 kubernetes 클러스터에 배포할 수 있습니다. 제공되는 웹 UI를 통해 배포할 jar 파일의 입력만으로 간단히 kubernetes 에 배포하고, 이를 한눈에 관리할 수 있도록 하였습니다. 또한 Rolling Update, Canary Update, Blue/Green Deployment 등 다양한 배포 전략을 지원하여 사용자의 환경에 따른 배포 전략을 수립할 수 있도록 하였습니다. ( Free-Trial 서비스에서는 Rolling Update 만 지원합니다. )


무료로 제공되는 TKS Console(Free-Trial) 서비스로 차세대 Kubernetes 배포관리 솔루션을 경험해보세요.
 > Free-Trial 서비스는 2022-12-31일 까지 제공하며, 예고 없이 종료 될 수 있습니다.
 > 사용문의 : tks-dev@sktelecom.com
