# tks cluster
TKS Kubernetes cluster에 대한 명령을 수행한다. 
```
$ tks cluster -h
Operation for TKS Cluster

Usage:
  tks cluster [flags]
  tks cluster [command]

Available Commands:
  create      Create a TKS Cluster.
  delete      Delete a TKS Cluster.
  list        Show list of clusters.
  show        Show cluster details.

Flags:
  -h, --help   help for cluster

Global Flags:
      --config string   config file (default is $HOME/.tks-client.yaml)
  -v, --verbose         verbose output

Use "tks cluster [command] --help" for more information about a command
```

## tks cluster create
TKS Kubernetes cluster를 생성한다. `.tks-client.yaml`에서 정의한 contractId와 cspId를 사용하기 때문에 cluster name만 주어도 클러스터 생성이 가능하고, 옵션 파라미터를 통해 별도의 id를 사용할 수 있다. 
```
$ tks cluster create -h
Create a TKS Cluster to AWS.

Example:
tks cluster create <CLUSTERNAME>

Usage:
  tks cluster create [flags]

Flags:
      --contract-id string     Contract ID
      --csp-id string          CSP ID
  -h, --help                   help for create
      --machine-replicas int   machine replicas of worker node (default 3)
      --machine-type string    machine type of worker node
      --num-of-az int          Number of availability zones in selected region (default 3)
      --region string          AWS Region
      --ssh-key-name string    SSH key name for EC2 instance connection

Global Flags:
      --config string   config file (default is $HOME/.tks-client.yaml)
  -v, --verbose         verbose output
```
### Options
- `contract-id`: 사용하는 TKS api서비스의 고유값이며, 최초 설치시 지정된 값을 사용한다.

- `csp-id`: 사용하는 TKS api서비스의 고유값이며, 최초 설치시 지정된 값을 사용한다.

- `machine-replicas`: worker node의 개수를 지정할 수 있다. num-of-az의 배수만 지원한다.

- `machine-type`: node의 flavor spec을 지정할 수  있다. 기본값은 `t3.large`이며, 설정 가능한 값은 [aws 페이지](https://aws.amazon.com/ko/ec2/instance-types/)를 참고한다. 

- `num-of-az`: 클러스터의 컨트롤플레인 노드가 설치될 Availability Zone의 개수를 의미한다. 기본값은 `3`이며, single 컨트롤플레인을 사용할 경우 `1`을 사용한다. 

- `region`: 클러스터가 배포될 aws region을 의미하며, 기본값은 ap-northeast-2(서울)이다.

- `ssh-key-name`: 클러스터 bastion node에 접속할 때  사용할 ssh keypair이름을 지정할 수 있으며, 기본값은 tks-seoul이다.

## tks cluster list
TKS Kubernetes cluster 리스트를 출력한다. `--long` 옵션을 사용하면 좀 더 자세한 정보가 출력된다.
```
$ tks cluster list -h
Show list of clusters.

Example:
tks cluster list (--long)

Usage:
  tks cluster list [flags]

Flags:
  -h, --help   help for list
  -l, --long   Print detail information

Global Flags:
      --config string   config file (default is $HOME/.tks-client.yaml)
  -v, --verbose         verbose output
```

## tks cluster show
TKS Kubernetes cluster의 ID를 통해 cluster의 상세 정보를 출력한다. 

```
$ tks cluster show -h
Show cluster details.

Example:
tks cluster show <CLUSTER_ID>

Usage:
  tks cluster show [flags]

Flags:
  -h, --help   help for show

Global Flags:
      --config string   config file (default is $HOME/.tks-client.yaml)
  -v, --verbose         verbose output
```

