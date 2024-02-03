## 0\. 개요

---

<img src="https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FciVFMw%2FbtsEmQxw1co%2FGzHlCkDKvwRNlywexbI9Y1%2Fimg.jpg" height="300" alt="이미지 설명">



이번에는 Docker에 대해서 제가 공부한 내용을 정리하는 시간을 가져보고자 합니다. docker가 무엇이길래, 이걸로 프로젝트 배포를 관리하고, 꼭 배워야 한다고 하는 것일까?

## 1\. Docker를 알기위한 Container

---

<img src="https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FbH7LHq%2FbtsEmqy5A3G%2FSuDk38LdH6VMU2LawBsZ8K%2Fimg.png" height="300" alt="이미지 설명">


Docker의 마크를 보면, 배위에 컨테이너가 쌓여있는 듯한 그림이 존재합니다. 왜 이렇게 Docker를 비유했을까??

<img src="https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2F2HfMo%2FbtsEj5P0GMs%2Fb9HbFpk4TE0FckvLydmTFK%2Fimg.png" height="300" alt="이미지 설명">


말콤 맥린(Malcolm McLean)이라는 20세기 초반, 자동차 운수업으로 매우 성공한 사람이 있었습니다. 자동차를 팔면서, 에로사항이 발생했습니다. 항구가 존재하면, 항구의 입구를 통해서 자동차를 담은 트럭이 들어오고, 배앞으로 와서 노동자들이 자동차를 내려서 배에 싣고... 이 작업을 하는동안 다른 트럭들은 대기를 하고... 이렇게 엄청난 트래픽이 몰리면서 구조적으로 비효율적이었습니다.

<img src="https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FbCiyWS%2FbtsEmrx1hPY%2FDUk04x154jjfzL2jIgISrk%2Fimg.png"  height="300" alt="이미지 설명">


여기서 container라는 개념이 생겨났습니다. 노동자들이 트럭이 자동차를 내릴 필요가 있었던 이전방식과 달리 외부에서 항구로 차를 싣을 컨테이너를 가져와서 대형 기계가 컨테이너를 들어서 항구에 적재하고, 트럭은 할일을 다했으니 그냥 가면 됩니다. 컨테이너채로 싣어버리니까 노동자의 일도줄고, 시간도 빠르고, 트래픽도 줄어들게 되었습니다.

받는 쪽에서도 배가 들어오면, 컨테이너를 기계로 싣어버리고, 트럭에 컨테이너에 그대로 싣어서 내보내는 간편함이 있었습니다. 이것이 컨테이너의 발명입니다. 그리고 Docker는 프로그래밍적으로 컨테이너를 관리하는 프로그램입니다.

## 2\. Docker??

---

<img src="https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FAQHx0%2FbtsEndzfbh8%2FJWYh4yaVUtnkB2EFkCTM40%2Fimg.jpg"  height="300" alt="이미지 설명">


아까 배위에 컨테이너를 올리듯이, Docker는 나의 컴퓨터 위에 OS를 올립니다. OS에는 JDK, Git, Python ...등등의 많은 프로그램이 설치되어 있습니다. 통째로 한번에 설치해서 올릴 수 있는 것 입니다. 또 이렇게 만들어진 컨테이너를 다른 컨테이너와 상호작용을 해서 한번에 올리거나 한번에 내릴 수도 있습니다. 이것을 Docker-compose라고 합니다.  이렇게 Docker container는 여러 프로그램을 한장에 옮길 수 있으므로, 잘 만들어놓은 컨테이너가 있으면 다른 컴퓨터에서도 동일하게 환경세팅을 쉽게 할 수 있습니다.

## 3\. Docker, Docker-compose, Docker-hub

---

<img src="https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FcM8dTg%2FbtsEmqy5UyG%2FQYiCi6CtkiYmKZJh9oDkW0%2Fimg.jpg"  height="300" alt="이미지 설명">


Docker는 컨테이너를 만들고 실행을 하고, 컨테이너를 구성할 수 있게 도와주는 기능을 제공합니다. 예를들어 떡볶이라는 컨테이너를 만들어서 떡, 파, 오뎅 등을 싣을 수 있습니다. 

Docker-compose는  다른 컨테이너와 상호작용할 수 있게 해줍니다. 예를들어 불고기라는 컨테이너를 떡볶이가 실행되면 같이 실행되도록 할 수 있습니다. 최소 두 개이상의 컨테이너를 실행하는 방법입니다.

Docker-hub([https://hub.docker.com/](https://hub.docker.com/))는 Github와 같다고 생각하면 편하다. 클라우드 서버에 개인이나 회사가 완성한 컨테이너를 올려서 공유하고, 통째로 다운받을 수 있습니다. repository와 같은 느낌의 컨테이너 관리 저장소이다.

## 4\. Docker-Desktop, Docker-compose 설치

---

### Docker-Desktop

---

[https://www.docker.com/products/docker-desktop/](https://www.docker.com/products/docker-desktop/)

 [Docker Desktop: The #1 Containerization Tool for Developers | Docker

Docker Desktop is collaborative containerization software for developers. Get started and download Docker Desktop today on Mac, Windows, or Linux.

www.docker.com](https://www.docker.com/products/docker-desktop/)

Docker-Desktop을 설치해줍니다. 

<img src="https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2Fc5vzpp%2FbtsEmMPqGoT%2FwRWA1rijAZl07PzqBJhM2k%2Fimg.png"  height="300" alt="이미지 설명">


여기서 중요한 점은 제어판 > 프로그램 및 기능  > Windows 기능에서 Linux용 Windwos 하위 시스템이 깔려있어야 합니다. Docker는 리눅스 시스템으로 돌아가므로, Docker Desktop을 설치하면 해당 옵션이 생성될 것 입니다. 체크해서 활성화 되어 있는지 확인해줍니다.

```
docker --version
```

도커가 자 설치되어 있는지 cmd창에서 확인할 수 있습니다.

```
docker run -d -p 80:80 docker/getting-started
```

예시로 한번 컨테이너를 받아서 실행시켜봅니다.

나중에 다시 설명하긴 할텐데, docker/getting-started라는 컨테이너를 run = 실행합니다. 만약 해당 컨테이너가(이미지) 내 컴퓨터에 없으면 다운받아서 실행합니다. 80:80으로 포트포위딩을해서 -d옵션으로 백그라운드 실행을 합니다.

<img src="https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FnUWce%2FbtsEmDZGqQu%2FvopXmpjvMngEBISYg8DFxk%2Fimg.png"  height="300" alt="이미지 설명">


그럼 이렇게 Docker-Desktop에 새로운 컨테이너가 활성화 됩니다. 

<img src="https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FcIiCU3%2FbtsEnO0qMBj%2FCpkyGno8E5TNS5k2DXKf1k%2Fimg.png"  height="400" alt="이미지 설명">


80포트로 실행중이니 localhost:80으로 진입하면 정상적으로 잘 실행되는 것을 확인할 수 있습니다.

### Docker-compose

---

[https://docs.docker.com/compose/install/standalone/](https://docs.docker.com/compose/install/standalone/)

해당 문서에서 docker-compose를 설치하는 방법을 알려주고 있습니다.

```
 Start-BitsTransfer -Source "https://github.com/docker/compose/releases/download/v2.24.5/docker-compose-windows-x86_64.exe" -Destination $Env:ProgramFiles\Docker\docker-compose.exe
```

해당 명령어를 파워쉘의 관리자모드에서 실행해줍니다.

```
docker-compose --version
```

해당 명령어가 잘 실행되면 잘 설치가 된 것입니다.

이번에는 Docker에 관해서, 설치에 대해서 얘기했습니다. 다음에는 Docker의 작동원리, 컨테이너에 대해서 알아보는 시간을 가져보려고 합니다.
