# Configuration
`tks`를 정상적으로 사용하기 위해서는 TKS api 서비스 url과 contract id, csp id 정보가 필요하다.

## TKS api 서비스
TKS api 서비스는 `tks-cluster-lcm`, `tks-contract`, `tks-info`로 구성되며, 어드민 클러스터의 tks 네임스페이스에서 확인할 수 있다.
```
# admin 클러스터

# Nodeport인 경우
$ kubectl get svc -n tks

# Ingress를 사용할 경우
$ kubectl get ing -n tks
```

## contract ID, csp ID
`tks`를 통해 TKS api 서비스와 통신하기 위해서는 TKS api서비스 고유의 contract id와 csp id를 알아야한다.
```
# admin 클러스터
$ kubectl get cm tks-cm -n tks
```

## .tks-client.yaml 설정
TKS api 서비스 url과 contract id, csp id 값을 `.tks-config.yaml`로 설정한다.
```
$ cat ~/.tks-config.yaml
tksClusterLcmUrl: tks-cluster-lcm.com
tksInfoUrl: tks-info.com
tksContractUrl: tks-contract.com
contractId: c947d800-ac43-4bab-a8e1-4ceaa0ffec98
cspId: f84df193-f6c8-45ad-867c-c0bcc48f09e5
```
