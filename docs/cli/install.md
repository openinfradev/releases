# Installation
`tks`는 Linux, MAC, Windows 환경에 설치가능하다. tks github repo에서 바이너리를 다운로드 받거나 소스파일을 직접 빌드하여 설치한다.

## Github Repo에서 다운로드
`tks` [github repo](https://github.com/openinfradev/tks-client/)의 릴리즈 페이지에서 사용하려는 시스템에 맞는 바이너리를 다운로드한다.
```
$ VERSION=2.0.0-rc2
$ wget https://github.com/openinfradev/tks-client/releases/download/v${VERSION}/tks-client_${VERSION}_Linux_x86_64.tar.gz
$ tar xvzf tks-client_${VERSION}_Linux_x86_64.tar.gz
LICENSE
README.md
tks
$ ./tks
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
## 소스 빌드
`tks`는 소스 빌드에 [task](https://taskfile.dev/)를 사용한다. 
```
$ git clone git@github.com:openinfradev/tks-client.git
$ cd tks-client/
$ task build
task: [build] GOFLAGS=-mod=mod go build -o bin/tks main.go
$ ./bin/tks
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
