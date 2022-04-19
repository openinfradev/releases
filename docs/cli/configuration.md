
# Configuration

`tks`를 정상적으로 사용하기 위해서는 TKS API 서비스 URL 정보가 필요하다.


## TKS API 서비스

어드민 클러스터의 `tks` 네임스페이스에서  `tks-cluster-lcm`, `tks-contract`, `tks-info`의 EXTERNAL-IP를 확인한다.

```

# admin 클러스터

$ kubectl get svc -n tks

NAME            TYPE            CLUSTER-IP      EXTERNAL-IP                     PORT(S)         AGE

tks-batch       ClusterIP       10.96.56.66     <none>                          9110/TCP        8d

tks-cluster-lcm LoadBalancer    10.111.51.12    <TKS-CLUSTER-LCM-EXTERNAL-IP>   9110:30361/TCP  13d

tks-contract    LoadBalancer    10.103.47.6     <TKS-CONTRACT-EXTERNAL-IP>      9110:32426/TCP  13d

tks-info        LoadBalancer    10.105.57.15    <TKS-INFO-EXTERNAL-IP>          9110:30582/TCP  13d

```


## .tks-client.yaml 설정

TKS api 서비스 url를 `${HOME}/.tks-client.yaml`로 설정한다.

```

$ tee ~/.tks-client.yaml << EOF

tksClusterLcmUrl: <TKS-CLUSTER-LCM-EXTERNAL-IP>:9110

tksInfoUrl: <TKS-CONTRACT-EXTERNAL-IP>:9110

tksContractUrl: <TKS-INFO-EXTERNAL-IP>:9110

EOF
```
