## 0\. 개요

---

[##_Image|kage@ciVFMw/btsEmQxw1co/GzHlCkDKvwRNlywexbI9Y1/img.jpg|CDM|1.3|{"originWidth":792,"originHeight":269,"style":"alignCenter"}_##]

이번에는 Docker에 대해서 제가 공부한 내용을 정리하는 시간을 가져보고자 합니다. docker가 무엇이길래, 이걸로 프로젝트 배포를 관리하고, 꼭 배워야 한다고 하는 것일까?

## 1\. Docker를 알기위한 Container

---

[##_Image|kage@bH7LHq/btsEmqy5A3G/SuDk38LdH6VMU2LawBsZ8K/img.png|CDM|1.3|{"originWidth":373,"originHeight":286,"style":"alignCenter"}_##]

Docker의 마크를 보면, 배위에 컨테이너가 쌓여있는 듯한 그림이 존재합니다. 왜 이렇게 Docker를 비유했을까??

[##_Image|kage@2HfMo/btsEj5P0GMs/b9HbFpk4TE0FckvLydmTFK/img.png|CDM|1.3|{"originWidth":1100,"originHeight":500,"style":"alignCenter"}_##]

말콤 맥린(Malcolm McLean)이라는 20세기 초반, 자동차 운수업으로 매우 성공한 사람이 있었습니다. 자동차를 팔면서, 에로사항이 발생했습니다. 항구가 존재하면, 항구의 입구를 통해서 자동차를 담은 트럭이 들어오고, 배앞으로 와서 노동자들이 자동차를 내려서 배에 싣고... 이 작업을 하는동안 다른 트럭들은 대기를 하고... 이렇게 엄청난 트래픽이 몰리면서 구조적으로 비효율적이었습니다.

[##_Image|kage@bCiyWS/btsEmrx1hPY/DUk04x154jjfzL2jIgISrk/img.png|CDM|1.3|{"originWidth":777,"originHeight":559,"style":"alignCenter","width":537,"height":386}_##]

여기서 container라는 개념이 생겨났습니다. 노동자들이 트럭이 자동차를 내릴 필요가 있었던 이전방식과 달리 외부에서 항구로 차를 싣을 컨테이너를 가져와서 대형 기계가 컨테이너를 들어서 항구에 적재하고, 트럭은 할일을 다했으니 그냥 가면 됩니다. 컨테이너채로 싣어버리니까 노동자의 일도줄고, 시간도 빠르고, 트래픽도 줄어들게 되었습니다.

받는 쪽에서도 배가 들어오면, 컨테이너를 기계로 싣어버리고, 트럭에 컨테이너에 그대로 싣어서 내보내는 간편함이 있었습니다. 이것이 컨테이너의 발명입니다. 그리고 Docker는 프로그래밍적으로 컨테이너를 관리하는 프로그램입니다.

## 2\. Docker??

---

[##_Image|kage@AQHx0/btsEndzfbh8/JWYh4yaVUtnkB2EFkCTM40/img.jpg|CDM|1.3|{"originWidth":750,"originHeight":422,"style":"alignCenter","width":501,"height":282}_##]

아까 배위에 컨테이너를 올리듯이, Docker는 나의 컴퓨터 위에 OS를 올립니다. OS에는 JDK, Git, Python ...등등의 많은 프로그램이 설치되어 있습니다. 통째로 한번에 설치해서 올릴 수 있는 것 입니다. 또 이렇게 만들어진 컨테이너를 다른 컨테이너와 상호작용을 해서 한번에 올리거나 한번에 내릴 수도 있습니다. 이것을 Docker-compose라고 합니다.  이렇게 Docker container는 여러 프로그램을 한장에 옮길 수 있으므로, 잘 만들어놓은 컨테이너가 있으면 다른 컴퓨터에서도 동일하게 환경세팅을 쉽게 할 수 있습니다.

## 3\. Docker, Docker-compose, Docker-hub

---

[##_Image|kage@cM8dTg/btsEmqy5UyG/QYiCi6CtkiYmKZJh9oDkW0/img.jpg|CDM|1.3|{"originWidth":780,"originHeight":439,"style":"alignCenter","width":627,"height":353}_##]

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

[##_Image|kage@c5vzpp/btsEmMPqGoT/wRWA1rijAZl07PzqBJhM2k/img.png|CDM|1.3|{"originWidth":688,"originHeight":488,"style":"alignCenter"}_##]

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

[##_Image|kage@nUWce/btsEmDZGqQu/vopXmpjvMngEBISYg8DFxk/img.png|CDM|1.3|{"originWidth":1149,"originHeight":226,"style":"alignCenter"}_##]

그럼 이렇게 Docker-Desktop에 새로운 컨테이너가 활성화 됩니다. 

[##_Image|kage@cIiCU3/btsEnO0qMBj/CpkyGno8E5TNS5k2DXKf1k/img.png|CDM|1.3|{"originWidth":700,"originHeight":655,"style":"alignCenter"}_##]

80포트로 실행중이니 localhost:80으로 진입하면 정상적으로 잘 실행되는 것을 확인할 수 있습니다.

### Docker-compose

---

[https://docs.docker.com/compose/install/standalone/](https://docs.docker.com/compose/install/standalone/)

 [Install Compose standalone

How to install Docker Compose - Other Scenarios

docs.docker.com](https://docs.docker.com/compose/install/standalone/)

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