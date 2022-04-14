# AWS Reference Architecture 
AWS에 IaaS 구성은 일반적인 AWS 가이드에 따라 구축 한다.   
Kubnernete node들(Master node, Worker node)은 Internet에 직접 연결되지 않는 AWS Private subnet에 존재하면, 각 node들은 Private IP만을 갖는다.
Kubernetes node등은 Avaiable zone들로 분산되어 Reliablility를 강화했다.    
Admin Cluster와 User Cluster는 그 구조가 같으며, 별도 독립 VPC에 구성된다. 따라서 비록 Admin Cluster와 User Cluster가 같은 AWS Account에 속해 있더라도, Internet을 통해 연결된다.  
   
   
![aws-ref](../assets/images/aws-ref.png)

아래는 Kubernetes node들의 Network 경로다.   
![aws-ref-nw](../assets/images/aws-nw.png)