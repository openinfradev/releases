# tks service
tks cluster에 설치될 service에 대한 명령을 수행한다. service는 LMA와 Service mesh가 있으며, LMA는 로깅과 모니터링 서비스로 구성되며 로깅 서비스의 경우 Loki와 Elastic(EFK)를 지원하고, 기본 로깅 서비스는 Loki이다.
```
$ tks service -h
Operation for TKS Service

Usage:
  tks service [flags]
  tks service [command]

Available Commands:
  create      Create a TKS Service.
  delete      Delete a TKS Service.
  list        Show list of service.

Flags:
  -h, --help   help for service

Global Flags:
      --config string   config file (default is $HOME/.tks-client.yaml)
  -v, --verbose         verbose output

Use "tks service [command] --help" for more information about a command.
```

## tks service create 
tks cluster에 tks service를 설치한다. 설치할 클러스터 ID와 설치할 서비스명이 필요하다. 서비스명은 `LMA`와 `LMA_EFK`, `SERVICE_MESH`만 사용할 수 있다.
```
 tks service create -h
Create a TKS Service. supported: LMA,LMA_EFK,SERVICE_MESH

Example:
tks service create --cluster-id <CLUSTERID> --service-name <LMA,LMA_EFK,SERVICE_MESH>

Usage:
  tks service create [flags]

Flags:
      --cluster-id string     Cluster ID
  -h, --help                  help for create
      --service-name string   Service Name

Global Flags:
      --config string   config file (default is $HOME/.tks-client.yaml)
  -v, --verbose         verbose output
```

## tks service delete
tks cluster에 설치된 service를 삭제한다. 설치된 클러스터 ID와 삭제할 서비스 ID를 사용한다.
```
$ tks service delete -h
Delete a TKS Service.

Example:
tks service delete <SERVICE ID>

Usage:
  tks service delete [flags]

Flags:
  -h, --help   help for delete

Global Flags:
      --config string   config file (default is $HOME/.tks-client.yaml)
  -v, --verbose         verbose output
```

## tks service list
tks 클러스터에 설치된 서비스 리스트를 요청한다.
```
$ tks service list -h
Show list of service.

Example:
tks service list <CLUSTER ID>

Usage:
  tks service list [flags]

Flags:
  -h, --help   help for list

Global Flags:
      --config string   config file (default is $HOME/.tks-client.yaml)
  -v, --verbose         verbose output
```
