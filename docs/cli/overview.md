# TKS CLI Manual
`tks`는 쿠버네티스 클러스터와 서비스에 대한 관리기능을 제공하는 CLI 툴로써 TKS api service와 gRPC 프로토콜을 사용하여 통신한다.
```
$ tks
   ______ __ __ ____  _____ __ _            __
  /_  __// //_// __/ / ___// /(_)___  ___  / /_
   / /  / ,<  _\ \  / /__ / // // -_)/ _ \/ __/
  /_/  /_/|_|/___/  \___//_//_/ \__//_//_/\__/

TKS Client is CLI client for using TKS Service.
For more: https://github.com/openinfradev/tks-client/

Usage:
  tks [command]

Available Commands:
  cluster     Operation for TKS Cluster
  completion  generate the autocompletion script for the specified shell
  endpoint    Operation for Thanos Endpoint
  help        Help about any command
  service     Operation for TKS Service

Flags:
      --config string   config file (default is $HOME/.tks-client.yaml)
  -h, --help            help for tks
  -t, --toggle          Help message for toggle
  -v, --verbose         verbose output

Use "tks [command] --help" for more information about a command.
```

