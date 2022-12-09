# About Free-Trial


SKT Enterprise Container Solution은 그 동안 SKT가 공개해 왔던 Open Source를 활용하여 구성된 Production level의 Kubernetes 배포관리 Solution 입니다. SKT Enterprise Container Solution 의 많은 Feature 중 대표적인 기능을 UI 로 구현하여, 누구나 쉽게 웹 UI 를 통해 SKT Enterprise Container Solution 서비스를 경험해 볼 수 있도록 하기 위해 FreeTrial 서비스를 출시 하였습니다.

저희는 kubernetes 도입 고객이 어려움을 겪는 대표적인 허들 몇 가지에 집중 하였습니다.

- **Provisioning**    
  당연하게도 kubernetes 클러스터 설치입니다. kubernetes 클러스터 구축을 도와 주는 많은 솔루션이 있으나, 프로덕션에서 사용할 수 있을 정도까지의 수준 높은 프로비저닝 도구는 많지 않습니다. 또한 클러스터를 설치할 머신 준비 부터 방화벽, 소프트웨어까지, 고려해야 하는 많은 선택지가 있으며, 높은 전문성을 요구합니다.
- **Monitoring**      
  구축한 클러스터가 유효한지, 시스템/어플리케이션 레벨의 모니터링 솔루션을 구축해야 합니다. 다양한 많은 소프트웨어가 있으나 즉시 사용할 만큼의 모니터링 솔루션을 구축하기 위해서는 역시 많은 노력과 전문성이 필요합니다. 
- **Application Deployment**        
  클러스터 구축에 성공했다고 하더라도 실제로 사용자 어플리케이션을 배포/관리하는데 또 다른 높은 허들이 존재합니다. kubernetes 에 대한 이해가 선행되어야 하기에 어플리케이션을 클러스터에 배포하는데 많은 어려움을 겪을 수 밖에 없고, kubernetes 의 다양한 장점을 활용하려면 높은 수준의 전문성이 필요합니다.


TKS Console 은 이 모든 허들을 최대한 낮추는데 집중했습니다. 

- **Stack**    
  사용자의 선택지를 최소화하고 production ready 수준의 안정적이고 파워풀한 소프트웨어를 한번에 제공하려고 노력 하였습니다. 클러스터와 서비스를 하나로 묶어 내부적으로 검증된 상태의 클러스터와 서비스를 클릭 한번으로 제공합니다. 뿐만아니라 이렇게 제공된 클러스터와 서비스는 "Infra as a code"의 수준을 넘어 100% gitOps 방식으로 완전히 추상화되어 관리되므로 투명하고 신속한 인프라 관리를 가능케 하였습니다.
- **Service**    
  스택에 포함된 pre built-in 서비스는 kubernetes 클러스터와의 종속성까지 검증된 상태로 제공이 되므로 아무런 사전 작업이 없이 그 즉시 사용할 수 있는 수준의 서비스를 제공합니다.
    - **Logging, Monitoring, Alerting**    
      Logging, Monitoring, Alerting 기능으로 제공되는 "LMA" 서비스는 built-in dashboard 등과 함께 제공되어 즉시 kubernetes 의 세밀한 부분까지 모니터링이 가능합니다.    
      > [LMA] 설명]()   
    - **Service Mesh**    
      MSA 개발에 필요한 다양한 도구들이 클러스터와 함께 세팅된 상태로 제공됩니다. 
      > [SERVICE MESH] 설명]()   
- **Continuous Deployment**    
  사용자 어플리케이션 배포 역시 웹 UI 를 통해 단순한 클릭만으로 쉽게 Kubernetes 에 배포할 수 있으며, Rolling Update, Canary, Blue/Green 등 다양한 배포 전략을 지원하려고 준비중에 있습니다.


무료로 제공되는 TKS Console(Free-Trial) 서비스로 진보된 방식의 Kubernetes 배포관리 솔루션을 경험해보세요.
 > Free-Trial 서비스는 2022-12-31일 까지 서비스를 제공합니다. 이 후 모든 리소스가 삭제되며 복구 할 수 없습니다.   
 > 사용문의 : tks-dev@sktelecom.com

