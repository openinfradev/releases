# Architecture Overview
SKT Enterprise Kubernetes Solution은 2종의 Clutser로 구성된다.   
   
- **Admin Cluster**   
   Admin Cluster는 Decapod가 설치된 Cluster로 서비스를 API로 제공하기 위한  Micro Serivce로 구성된 API Service등과 운영을 위한 툴로 구성되어 있다.
   Admin Cluster는 Platform 관리자가 관리하는 Cluster며, User Cluster의 LCM을 제공하는 Backend이다.   
- **User Cluster**   
   User Cluster는 제공하고자 하는 서비스가 운영되는 Cluster다. User Cluster의 사용자는 개발자/서비스운영자 이다.   
   User Cluster자체는 Admin Cluster에 의해 자동 관리된다.   
   
![argch-deep](../assets/images/arch-deep.png)