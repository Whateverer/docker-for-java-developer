# docker-for-java-developer
Udemy Docker - Java 개발자를 위한 완벽 실습 과정 정리
# 섹션 1장 소개
# 섹션 2장 Docker 소개
## 2. Docker 소개
각 실행환경이 다른데 다른 개발자가 자신의 컴퓨터에서 war파일을 전송해줘서 내 컴퓨터에서 실행하려고 할 때, 실행환경이 달라 제대로 실행되지 않는다.
이런 상황을 언젠가는 분명 마추칠 것이다. 그 때 Docker를 사용하면 효과적이다.

## 3. 이미지 및 컨테이너
보통의 java 애플리케이션은 jar 파일이나 war 파일로 배포 담당자가 배포한다.
하지만 Docker의 경우는 다르다. 격리되어 있는 애플리케이션으로 실행되는 jar파일을 배포하지 않고 컨테이너를 실행하는 것이다.
#### 이미지
Docker에서 이미지란 컨테이너를 만들 모든 환경설정들을 포함한 것이다. ex) 한 이미지 안에 java 11, tomcat 등
#### 컨테이너
완전하고 독립적인 환경. 이미지의 인스턴스로, 실행하여 이미지 중 하나를 인스턴스화 한 것    
-> 내가 이해한 것 : java로 비유하자면, 이미지는 클래스고 클래스를 통해 생성된 인스턴스가 컨테이너라고 생각된다.
### 이미지 vs 컨테이너
- 구축하는 엔티티가 이미지이고, 그 이미지를 실행하면 실행 컨테이너가 된다.
- 즉, 하나의 이미지를 여러 번 실행할 수 있으며 그렇게 하면 동일한 이미지를 수행하는 여러 개의 컨테이너가 생성된다.
- 그렇게 해서 하나의 이미지로 여러 군데에서 동일한 환경의 컨테이너를 실행시킬 수 있다.
=> 배포자에게 jar나 war파일이 아닌, Docker 이미지를 전달하면 된다.

## 4. 컨테이너 vs 가상머신
#### 컨테이너
- 컨테이너는 전체 운영체제를 포함하지 않으므로 가상 머신보다 훨씬 가볍고 효율적이다.
- 각 컨테이너에는 Linux의 유틸리티 컬렉션이 포함되어 있다.(ex. ubuntu, redhat 등) 하지만 모든 컨테이너에는 Linux의 커널은 포함되어 있지 않다. (그래서 컨테이너안에 독립적인 os가 없다고 표현한다.)
#### 가상머신 
- 가상머신에는 각각의 커널이 존재한다. 
- 그래서 가상머신은 비교적 무겁고 느리다.

# 섹션 3장 Docker 설치
## 5. BIOS에서 가상화 지원 실행
## 6. 개발 및 프로덕션 시 Docker
Docker를 이용하여 image를 빌드하고 컨테이너를 실행하는 최종 목표는 로컬에서 개발하고 테스트한 것과 동일한 이미지를 배포할 수 있게 되는 것
완벽히 같은 방식으로 실행되어야 한다.
Docker로 작업하는 데는 두 가지 측면이 있다.
- Local Docker
- targetting enviroment (공급자, 서버 등) => 여기에도 Docker를 설치해야 한다.

실제로 컨테이너는 Linux의 개념이다. 컨테이너는 Linux에서 실행되는 프로세스일 뿐이다.
### How to Run Docker Outside Linux? Linux 환경 밖에서 Docker는 어떻게 실행되는가?
native하게 원래 Docker는 Linux 밖에서 실행되지 않는다. 그래서 window나 mac을 사용하는 사람은 가상머신을 이용해야 한다. (Docker의 백그라운드에서 리눅스 기반의 OS가 실행되어야 함)

## 7. 이제 Docker Toolbox를 사용할 수 없음

## 8. 설치 옵션
### Window 10 Pro user 
- Docker Desktop 설치 (가상머신을 제공)
- Docker Desktop은 사실상 가상화된 Linux 머신이다.
- Window 10 Pro에 가상화가 내장되어 있어 Docker Desktop에서 이것을 이용한다.

### Mac Yosemite 10.10.3 or above
- Docker Desktop 설치

### Docker Desktop vs Docker Toolbox
- Docker Desktop은 내장된 Linux 가상 머신을 활용한다.
- Docker Toolbox는 타사 가상 머신 구현을 자동으로 다운로드한다.
- Oracle을 이용한 Oracle VirtualBox
