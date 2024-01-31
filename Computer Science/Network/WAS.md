## 서론

---

![이미지 설명](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FbNqdUE%2FbtsC33FX57u%2FjKhe1jnIlPwZ7v4UPgpmN1%2Fimg.png)

A군이 회사에 들어가게 되었습니다. 상사는 신입사원들에게 "우리 회사는 6대의 WAS를 가지고 있습니다!!" 라고 했습니다. A군은 "WAS가 뭐지? Web Application Server? 내가 알고있는 Apache와 같은 웹서버와는 다른건가?" 라는 생각이 들었습니다. 이번에는 WAS가 무엇인지에 대해서 알아보는 시간을 가지겠습니다.

## Web, Server, Web Server

---

### Web

---

[##_Image|kage@cAIKjH/btsC4upNv4N/C1YwiV3kEiyAoNArywboWk/img.png|CDM|1.3|{"originWidth":800,"originHeight":800,"style":"alignCenter","width":310,"height":310}_##]

웹(Web)은 인터넷을 기반으로 정보를 공유하고 검색할 수 있는 서비스이다.  웹을 통해 우리는 전 세계적으로 다양한 정보에 접근할 수 있으며, 이를 위해 다양한 기술과 프로토콜이 사용된다. 예시로, URL, HTTP, HTML이 존재한다.

-   URL(Uniform Resource Locator) :  웹에서 특정 자원의 위치를 지정하는 주소 체계입니다. URL을 통해 웹 브라우저는 특정 웹 페이지, 이미지, 동영상 등을 찾아서 요청하고 접근할 수 있습니다.  
      
    
-   HTTP(Hypertext Transfer Protocol) :  웹 상에서 데이터를 주고받는 데 사용되는 프로토콜입니다. 클라이언트(웹 브라우저)와 서버 간에 문서를 전송하고 서로 통신하기 위한 표준 프로토콜로 사용됩니다.  
      
    
-   HTML(Hypertext Markup Language) :  웹 페이지의 구조와 내용을 정의하는 마크업 언어입니다. HTML은 웹 브라우저가 정보를 해석하여 사용자가 볼 수 있는 형태로 표시합니다.

### Server

---

[##_Image|kage@bEmYaL/btsC4D1gs8K/EfisiQOzZu6ZEeyZJT2UbK/img.webp|CDM|1.3|{"originWidth":328,"originHeight":204,"style":"alignCenter","width":404,"height":251}_##]

서버(Server)는 클라이언트(일반적으로 웹 브라우저)로부터 요청을 받아들이고, 해당 요청에 대한 정보나 서비스를 제공하는 컴퓨터 시스템이다.

### Web Server

---

[##_Image|kage@ejC0Vv/btsDavAG51j/5hPcDiyAmGGrX0krcHQP3K/img.png|CDM|1.3|{"originWidth":796,"originHeight":260,"style":"alignCenter","width":784,"height":256}_##]

그렇다면, Web + Server인 웹 서버(Web Server)는 무엇일까?

**인터넷을 기반**으로 클라이언트에게 **웹 서비스를 제공**하는 컴퓨터 시스템을 의미한다. 클라이언트에서는 웹 서버에 URL과 HTTP에 맞는 요청을 하면, 서버는 요청을 기다리고, 웹 요청(Request = "HTTP, CSS, JS 파일을 줄래?")에 대한 데이터를 만들어서 응답(Response = "요청한 파일")을 해준다. 요청 데이터는 웹에서 처리할 수 있는 html,css,js,이미지 같은 정적인 데이터를 주게된다. Apache, Nginx, Microsoft IIS 등이 웹 서버의 예시이다. 아파치같은 웹 서버를 이용해서 우리의 개인 컴퓨터로도 간단한 웹서버를 만들 수 있다.

이러한 과정에서 html은 프로그래밍 언어가 아니므로 DB에서 데이터를 가져온다던가..라는 동작을 할 수 없었다. 또한 html, css,js와 같은 정적 데이터만 줄 수 있었기에, 동적 컨텐츠를 다룰 수 없었다. 뭔가 다른 프로그램으로 해치울 수 있는 방법이 있지 않을까.. 라는 생각이 점점 들기 시작했다.

## WAS(Web Application Server)

---

[##_Image|kage@wtbjU/btsC9l59OY8/ylshRiErLSN5Rzu8AaTV21/img.png|CDM|1.3|{"originWidth":800,"originHeight":275,"style":"alignCenter","width":783,"height":269}_##]

이 때, 등장한 것이 **WAS**(Web Application Server)로, 웹 애플리케이션을 실행하기 위한 서버를 가리킨다.  WAS는 웹 애플리케이션을 실행하는 데 필요한 환경을 제공하고, 동작시키는 기능을 제공하는 소프트웨어 프레임워크이다. 웹 어플리케이션을 실행시켜 필요한 기능을 수행하고 그 결과를 웹 서버에 전달하는 미들웨어 역할을 한다. 

WAS는 프로그램 실행환경, DB접속 기능 등을 제공하고 비즈니스 로직을 수행할 수 있다. 웹 서버의 기능과 웹 컨테이너의 기능을 더했다고 볼 수 있다. 웹 서버와 웹 컨테이너는 함께 작동하여 웹 애플리케이션을 완성하고 사용자에게 제공하는 데 기여한다. **정적 콘텐츠**는 웹 서버에서 처리되고, **동적 콘텐츠**는 웹 컨테이너에서 처리되어 웹 애플리케이션의 전체 기능이 제공된다.

[##_Image|kage@dzHpIK/btsC6U9V2UK/WKSTaKi1j8KbdbKrgMQRUk/img.png|CDM|1.3|{"originWidth":1071,"originHeight":280,"style":"alignCenter","width":757,"height":198}_##]

**웹 컨테이너** : 웹 컨테이너는 웹 서버에서 동적인 콘텐츠를 생성하고 실행하기 위한 환경을 제공한다. Java 기반에서는 JSP나 Servlet과 같은 서버 사이드 스크립트를 실행하고 이를 처리한다. 또한, 데이터베이스 연결, 비즈니스 로직 실행, 세션 관리 등을 수행한다. Java계열에서는 웹 애플리케이션 컨테이너라고도 부른다. tomcat, ibm websphere, jeus 등이 존재한다. 

### 여러대의 WAS를 쓰는 이유

---

[##_Image|kage@Tzig4/btsC6pbkU68/pkVlg6JI637EFN1ldG01k0/img.jpg|CDM|1.3|{"originWidth":500,"originHeight":522,"style":"alignCenter","width":404,"height":422}_##]

**여러 WAS**를 사용하는 경우에는 웹 서버나 다른 시스템들과 조합하여 웹 애플리케이션의 가용성, 성능, 보안 등을 향상시킨다.

-   **가용성 향상**: 여러 대의 WAS를 사용하면 하나의 WAS에 장애가 발생했을 때에도 다른 WAS가 이를 대신하여 서비스를 제공할 수 있어서 시스템의 가용성이 높아진다. 이는 사용자에게 지속적인 서비스를 제공하고 서비스 중단을 최소화할 수 있도록 도와준다.
-   **부하 분산**: 여러 대의 WAS를 사용하면 클라이언트 요청을 분산시켜 각 WAS에 동일한 부하가 가해지게 되므로 시스템의 부하를 분산하여 성능을 최적화할 수 있다.
-   **확장성**: WAS를 여러 대 사용함으로써 시스템의 성능을 향상시킬 수 있다. 필요에 따라 새로운 WAS 인스턴스를 추가하고 확장하여 서비스의 규모를 쉽게 키울 수 있다.
-   **병렬 처리 및 성능 향상**: 여러 WAS를 사용하면 요청을 병렬로 처리할 수 있으며, 이는 성능을 향상시키고 응답 시간을 단축시킬 수 있다.
-   **장애 대비 및 복구**: 여러 대의 WAS를 사용함으로써 장애가 발생했을 때에도 시스템의 정상적인 운영을 지원하고 빠른 복구를 할 수 있다.
-   **지역적 로드 밸런싱**: 다양한 지역에 WAS를 배치함으로써 지역적으로 로드를 분산시켜 지역별 성능을 최적화하고 사용자들에게 빠른 응답 시간을 제공할 수 있다.  
      
    이러한 여러 이점들은 여러 대의 WAS를 사용하는 경우에 얻을 수 있는 장점들로, 이를 통해 웹 애플리케이션의 성능, 가용성, 확장성을 향상시킬 수 있다.

여러 WAS를 사용하는 다양한 방법이 있다. 여기에는 로드 밸런싱과 역방향 프록시의 사용이 포함 된다.

[##_Image|kage@naT9R/btsC4xgmOpB/C3D4TbsopS1MIkzs9tnOBk/img.jpg|CDM|1.3|{"originWidth":640,"originHeight":400,"style":"alignCenter"}_##]

#### 로드 밸런싱 (Load Balancing)

여러 대의 WAS를 사용할 때, 클라이언트의 요청을 균등하게 분산하여 각 WAS 서버에 부하를 분산시키는 것이 중요하다. 이를 위해 로드 밸런서(load balancer)를 사용할 수 있다.  
로드 밸런서는 클라이언트의 요청을 여러 WAS 인스턴스로 분배함으로써 부하를 균형 있게 분산시킨다. 이는 각 WAS 서버에 골고루 부하를 분산하여 성능을 최적화하고, 가용성을 높이는데 도움이 된다.

[##_Image|kage@Ka2Kj/btsC53zj0e2/QxiFACxvOiQuf6TR8yony0/img.png|CDM|1.3|{"originWidth":1392,"originHeight":563,"style":"alignCenter","width":786,"height":318}_##]

#### 역방향 프록시 (Reverse Proxy)

역방향 프록시는 클라이언트와 WAS 사이에서 중개 역할을 하며, 보안과 성능 향상을 위한 기능을 수행한다.  
클라이언트로부터의 요청을 WAS로 전달하기 전에 역방향 프록시가 요청을 필터링하거나 보완하여 웹 애플리케이션을 보호할 수 있다. 이는 보안 측면에서 중요한 역할을 한다.  
또한, 역방향 프록시는 WAS에서 나오는 응답을 클라이언트에게 전달하기 전에 캐싱, 압축, SSL 암호화 등을 수행하여 성능을 향상시킬 수 있다.  
이렇게 WAS를 사용함으로써 로드 밸런싱과 역방향 프록시를 이용하여 서버의 부하 분산과 보안 강화, 성능 향상 등 다양한 부분에서 효과적으로 웹 애플리케이션을 관리할 수 있다.

더보기

**정방향 프록시(Forward proxy) vs 역방향 프록시(Reverse proxy)**

정방향 프록시와 역방향 프록시의 주요 차이점은 네트워크 아키텍처에서의 위치다. 정방향 프록시는 클라이언트와 인터넷 사이에 위치하며 역방향 프록시는 클라이언트와 서버 사이에 위치한다.  
  
또 다른 주요 차이점은 목적이다. 순방향 프록시는 주로 클라이언트에 개인정보를 제공하고 네트워크 제한을 우회하는 데 사용된다. 반면 역방향 프록시는 주로 서버의 성능, 보안, 확장성을 향상시키는 데 사용된다.

## 간단한 정리

---

[##_Image|kage@6yBaP/btsDfN85sqv/NDlonAPA1rCWnWjxkITklk/img.png|CDM|1.3|{"originWidth":180,"originHeight":180,"style":"alignCenter","width":272,"height":272}_##]

이처럼, "우리 회사는 6대의 WAS를 가지고 있습니다"라는 문장은 회사가 웹 애플리케이션 운영을 위해 여러 대의 WAS를 사용하고 있음을 의미하며, 이는 서비스의 가용성, 확장성, 성능 향상을 목적으로 노력하고 있다고 이해하면 될 것 같다.
