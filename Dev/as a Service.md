# IaaS

서버, 스토리지, 네트워크 등 인프라 자원만을 제공하는 서비스

Ex) AWS EC2, Vmware 등

# PaaS

공급자가 최종 사용자에게 배포 및 관리기능을 제공하는데 사용하는 서비스  

해당 프로세스와 관련된 인프라 또는 플랫폼을 구축하고 유지관리할 필요없이, 어플리케이션을 개발, 실행 및 관리할 수 있도록 해준다.

앱의 개발 및 시작, 설정에 관련된 인프라를 만들고 유지보수 하는 복잡함 없이 고객이 어플리케이션을 개발, 실행, 관리할 수 있도록 도와주는 형태.  

Ex) AWS RDS, Google Cloud Platform 등

## Examples

### Docker

표준 컨테이너 인프라로써, 컨테이너에서 앱을 운영하고 관리하는데 필수적인 툴들을 제공한다.

- 컨테이너를 통한 PaaS를 가능하게 한다. (컨테이너를 사용한다는 것 자체가 PaaS 솔루션을 사용하고 있다는 것은 아님)
- 자동확장, 트래픽 라우팅, 로드 밸런싱등을 용이하게 하고 자동화하는 오케스트레이션 솔루션은 제공하지 않기때문에, PaaS에 접근하기 위해선 자동화와 관리가 포함된 오케스트레이션 기능이 필요하다.

# SaaS

소프트웨어를 구입해서 PC에 설치하지 않아도 웹에서 소프트웨어를 빌려 쓸 수 있다는 개념, 클라우드에서 모든 어플리케이션 서비스가 운영되는 것

Ex) Google Gmali, 캘린더, Docs등