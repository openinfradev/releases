
# SKT Container Platform Release Document

SKT Container Platform은 [Decapod][decapod] 기술을 기반으로, Kubernetes Cluster와 Kubernetes를 운영하기 위한 Add-on (CNI, CSI, Ingress Controller등), 그리고 다양한 서비스들(Monitoring, Service Mesh, App CICD, AI Ops등)을 All-in-One으로 제공하는 통합 컨테이너 관리 기능을 제공합니다.

더 나아가서, 하이브리드 및 멀티 클라우드 환경에서 사용자들이 자신이 원하는 형태의 다양한 CaaS (Container as a Service)를 제공할 수 있는 서비스 플랫폼으로 진화해가고 있습니다.
## Release Document
Release 문서사이트는 다음과 같은 내용을 담고 있습니다.

- Quick Start
- Release Note
- Architecture
- CLI manual
- API reference

---
## MKDocs
This site is built with [MkDocs][mkdocs] using [material theme][material-theme],  [mike][mike], [awesome pages plugin][awesome-pages-plugin], and [Slate][slate].

We also reference [RemoteCloud Document Site][remotecloud-docs] to set-up our document site.

### MKDcos Getting Started

- Installation: https://www.mkdocs.org/getting-started/
- Writing your docs: https://www.mkdocs.org/user-guide/writing-your-docs/

### MKDocs Material format 

Material for MkDocs is packed with many additional editing features. Please see the following link.

- [mkdocs material format reference](https://squidfunk.github.io/mkdocs-material/reference/)



[mkdocs]: https://github.com/mkdocs/mkdocs
[material-theme]: https://squidfunk.github.io/mkdocs-material/
[mike]: https://github.com/jimporter/mike
[slate]: https://github.com/slatedocs/slate
[awesome-pages-plugin]: https://github.com/lukasgeiter/mkdocs-awesome-pages-plugin
[remotecloud-docs]: https://github.com/RemoteCloud/public-documentation
[decapod]: https://github.com/openinfradev/decapod-docs