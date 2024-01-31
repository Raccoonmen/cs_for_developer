## 서론

[##_Image|kage@bWskZv/btsC9BHH6wD/cIpTS8B3HfCt3N6oKlOdAK/img.png|CDM|1.3|{"originWidth":780,"originHeight":780,"style":"alignCenter","width":399,"height":399}_##]

우리가 프로그램을 실행하면 프로세스가 실행됩니다.

하지만, 비슷한 개념으로 쓰레드라는 개념이 존재합니다. 그래서 쓰레드와 프로세스를 혼동하기도 합니다.

저도 두 개념의 차이점을 말하라고 한다면 잘 설명하지 못했습니다.

이번에는 두 개념에 대해서 알아보는 시간을 가지고자 합니다.

## Process, Thread?

---

### Program

---

[##_Image|kage@b36NVX/btsC312hy5a/gDvCPAJKQFpP98wL89yutK/img.png|CDM|1.3|{"originWidth":702,"originHeight":368,"style":"alignCenter","width":423,"height":222}_##]

프로그램은 명령어, 코드 및  정적인 데이터의 묶음이다. 

개발자들이 코드를 짜서 프로그래밍을 해서 프로그램을 만든다. 하지만 이걸 실행시키지 않으면 단순한 데이터 덩어리일 뿐이다. 프로그램을 살아있는 서비스로 만들기위해 프로세스가 되어야한다. 

### Process

---

[##_Image|kage@blwu4a/btsC9z4eSvM/j5Lck4fEEiKjtVLBntW5o1/img.png|CDM|1.3|{"originWidth":919,"originHeight":569,"style":"alignCenter","width":787,"height":487}_##]

**프로세스**란 프로세서에 의해 실행되는 프로그램이다. 혹은 운영체제로부터 시스템 자원을 할당 받는 작업의 단위라고 부른다. 간단하게 비유하자면, 피자 레시피는 그냥 글자가 있는 종이일 뿐이다. 하지만 레시피에 의해 피자가 되는 것처럼 코드 또한 실행되는 무엇이 되어야 하는데 이것이 프로세스이다.

프로세스가 되기위해서는 프로그램이 RAM(시스템 메모리)에 올라간다. 메모리에는 4가지 영역이 있다.

-   Code : 실행 명령을 포함하는 코드들이 저장되는 영역. CPU는 이 코드 영역에 있는 명령어를 순차적으로 실행한다.
-   Data : Static 변수 혹은 Global 변수들이 저장되는 영역. 프로그램이 실행될 때 메모리에 할당되며, 프로그램의 시작부터 끝까지 유지된다.
-   Heap : 동적 메모리를 할당하기 위한 영역.
-   Stack : 지역변수, 매개변수,  변환 값 등등 일시적인 데이터가 저장되는 영역.

프로세서는 RAM에 올라간 프로그램의 명령어를 순차적으로 실행하고, 이러한 명령어 실행을 통해 프로그램이 동작하게 된다. 따라서 프로세서는 RAM에 올라간 프로그램을 실행하는 역할을 담당한다.

[##_Image|kage@MK2Xf/btsC5XL1btb/sNQVoW1krtZNl2N9Q7arjK/img.png|CDM|1.3|{"originWidth":800,"originHeight":748,"style":"alignCenter","width":393,"height":367}_##]

보통의 사람들은 컴퓨터를 사용하면서 크롬을 쓰면서, 카카오톡도 쓰면서, 게임도 하면서... 등등 하나의 프로세스를 사용하기 보다는, 여러가지를 동시에 사용하고 싶어한다. 원래는 하나의 프로세스가 실행되고, Cpu를 점유하게되면, 다른 프로세스는 실행되지 못한다. 한마디로 유튜브로 노래듣다가 카카오톡을 키면 노래가 꺼진다는 말이다. 

[##_Image|kage@dSYgUf/btsDaxL2l9F/OVUcl6jySK4UfkS4H4Z9v1/img.png|CDM|1.3|{"originWidth":1280,"originHeight":720,"style":"alignCenter","width":506,"height":285}_##]

이를 해결하기 위해 다수의 프로세스를 동시에 실행하는 방법으로, 여러개의 프로세스를 시분할로 짧은텀을 반복하면서 전환하면서 실행하도록 한다. 예를들어 X, Y라는 프로세스가 있다고 하자.

1\. X라는 프로세스가 실행상태가 되며 CPU에 적재된다.

2\. Y프로세스는 준비상태로 존재한다.

3\. Y프로세스를 실행하기 위해 X프로세스가 준비상태가 된다.

4\. Y프로세스가 실행상태가 되며 CPU에 적재된다.

5\. ...반복

이러한 과정을 context switching이라고 한다. 이 때, 등장한 것이 경량화된 프로세스의 버전인 스레드이다.

### Thread

---

[##_Image|kage@wq4EK/btsC9xS1yb0/beB3kgrPOyTTViFwylPcik/img.jpg|CDM|1.3|{"originWidth":341,"originHeight":148,"style":"alignCenter","width":509,"height":221}_##]

#### **실행단위**

실행단위는 CPU core에서 실행하는 하나의 단위로, 프로세스와 스레드를 포함하는 단위이다. 실행단위가 프로세스일 때도 있고, 스레드일 때도 있다. 이게 무슨 소리일까? 스레드는 모든 프로세스에 존재한다. 위의 그림에서 왼쪽처럼 하나의 스레드를 가지고 있는 단일 스레드 프로세스를 프로세스라고 부른다. 오른쪽 그림처럼, 하나의 프로세스는 여러개의 스레드를 가질 수 있다.

#### **스레드**

**스레드**는 한 프로세스 내에서 구분되어진 실행단위이다. 위의 프로세스의 설명에서 프로세스에는 4가지 영역이 있다고 했었다. 하나의 프로세스에 다수의 스레드가 있을 때, 스레드는 자원을 공유한다. 스택 영역만 따로 존재하고, 코드 , 데이터, 힙 영역을 공통된 자원으로 사용한다. 공유되는 자원이 있다는 것은 Context Switching을 동작할 때, 모든 영역을 넣고 빼고 할 필요가 없어지므로 캐싱 적중률이 올라가게 된다.

[##_Image|kage@dMHEb6/btsC35cGBTR/6EpykeNQ2LkMNOV7veAejK/img.jpg|CDM|1.3|{"originWidth":236,"originHeight":214,"style":"alignCenter","width":279,"height":253}_##]

노래방을 예시로 들어보자.

노래방에서 노래를 하고 방에서 나오면, 노래방 기계, 마이크 ,스피커, 테이블, 의자 등등을 싹다 뗀다. 손님이 나오고, 노래방 기계 등등을 다시 설치하고 손님이 들어온다고 해보자. 이러한 방식은 비효율적이라는 것이다. 다음 손님도 역시 노래를 부를 것이므로 노래방 기계, 마이크 , 스피커 등등은 공통적으로 사용한다.  그래서 공통으로 사용하는 노래방 기계 등의 요소들은 냅두고 손님만 왔다갔다하면 효율적이라는 것이다.

한마디로 정리하자면, 프로세스는 프로그램이 실행된 것이고, 스레드는 한 프로세스 내에서 나뉘어진 하나 이상의 실행단위이다.

## Multi Process vs Multi Thread

---

Multi Process, Multi Thread이 두 개념은 모두 **처리방식의 일종**이다.

한 어플리케이션이 여러가지 일을 처리할 때가 있다. 이런 상황에 대한 두가지의 다른 처리방식을 의미한다.

### **멀티 프로세스**

[##_Image|kage@CpeRO/btsC5XZyWsj/PJfg5gUp06ZIDHMLnK81IK/img.png|CDM|1.3|{"originWidth":295,"originHeight":171,"style":"alignCenter","width":447,"height":259}_##]

예를들어 여러 사용자가 로그인을 하는 상황을 생각해보자. 한 프로세스는 하나의 로그인만 처리하므로 동시 처리를 못하게 된다. 그러므로 부모 프로세스가 fork를 통해서 자식 프로세스를 여러개 만들어서 일을 처리하도록 한다. 자식 프로세스는 부모와 별개의 메모리 영역을 확보한다.

[##_Image|kage@NspNA/btsC74X8qCi/AyXvlEHoQl7jR2cqIRSK80/img.jpg|CDM|1.3|{"originWidth":180,"originHeight":180,"style":"alignCenter","width":306,"height":306}_##]

**특징**으로는, 각 프로세스는 독립적이며, IPC를 사용한 통신을 한다. 예를들어, 여러명이 작업을 처리하는데 각자의 방이 따로따로 존재한다. 그러므로 다시 모여서 회의를 하려면 각자의 방을 나와서 이야기를 하고, 다시 각자의 방에 들어간다. 개별의 메모리를 차지하며 Context Switching 비용이 크다. 하지만 독립적이므로 동기화 작업이 필요없다는 장점이 있다.

### **멀티 스레드**

앞에서 스레드는 한 프로세스 내에서 구분되어진 실행단위라고 했었다. 이 단위는 한 프로세스에 하나의 스레드밖에 없다면 실행단위는 프로세스가 되는 것이고, 여러 스레드로 나누어져 있다면 멀티 스레드이다. 예를들어 우리가 VS code나 인텔리제이 같은 프로그램을 사용하는데, 코드를 보여주면서, 테스트도 가능하면서... 등등 여러개의 작업이 한 어플리케이션에서 나누어질 때 스레드가 작업을 담당한다. 

[##_Image|kage@ciFfCr/btsC76IpSZR/HTc5bMOybNTFJd12cPKXs0/img.jpg|CDM|1.3|{"originWidth":225,"originHeight":225,"style":"alignCenter","width":297,"height":297}_##]

**특징**으로는 스레드끼리 긴밀하게 연결되어 있다. 여러명이 한 회의실에서 작업을 한다고 생각하면 쉽다. 공유된 자원으로 통신비용을 절감하면서 메모리가 효율적으로 사용된다. 이런 이유로 Context Switching 비용이 줄어든다. 하지만 동기화를 신경써야하며 공유자원을 관리해줘야 효율적으로 사용할 수 있다.

### 멀티 스레드가 훨씬 좋은거 같은데 멀티 프로세스는 왜쓰는거야?

---

[##_Image|kage@bvFwca/btsC4fsPvKW/2qkjlHTtHm3HyJSceCGZqK/img.jpg|CDM|1.3|{"originWidth":326,"originHeight":155,"style":"alignCenter"}_##]

**인터넷 익스플로러**를 예시로 들어보면, 하나의 창에서 오류가 발생하면 창 모두가 동시에 꺼지게 된다. 이건 멀티 쓰레드를 이용했기 때문이다. 서로 긴밀하게 연결되어 있기 때문에 한 탭에 문제가 생기면, 전체 프로세스에 영향이 간다.

[##_Image|kage@RGBLy/btsC880hreu/pJ5looa072jYzN66jj7jok/img.png|CDM|1.3|{"originWidth":877,"originHeight":393,"style":"alignCenter","width":657,"height":294}_##]

반면에 **Chrome**은 각 탭을 별도의 프로세스로 처리한다. 따라서 개별 탭에서 오류가 발생하더라도 일반적으로 다른 탭은 영향을 받지 않고 작동할 수 있다. 오류가 발생한 특정 탭은 종료되거나 다시 로드될 수 있지만, 브라우저 전체가 종료되는 것은 아니다. 이는 Chrome의 각 탭이 독립적인 프로세스로 실행되어 다른 탭과 분리되어 있기 때문에 가능하다.