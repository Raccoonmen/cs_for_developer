## 0\. 개요

---

[##_Image|kage@dAfwKs/btsEcapjO0k/jkK3OSe3CtV1FoskuimZ00/img.jpg|CDM|1.3|{"originWidth":235,"originHeight":214,"style":"alignCenter","width":284,"height":259}_##]

이전의 포스팅에서 빌드 및 개발과 같은 내용에 대해서 정리를 했었습니다.

하지만 개발자가 수백,수천~ 그이상의 사용자가 사용하는 수천건의 로그가 발생하는 서비스를 주시하면서 서버가 꺼지면 켜주고, 일일히 파일을 올려서 배포해주고 등등의 작업을 해야한다면 잘시간도 없이 24시간 근무를 해야할 겁니다.

이를 위해서 우리는 테스트, 빌드, 배포, 로그 등등의 과정을 자동화를 통해서 서버를 관리해주어야 합니다. 이를위해서 CI/CD에 대해서 제가 아는 지식들을 적어보는 시간을 가져보겠습니다.

## 1\. DevOps

---

[##_Image|kage@o5iRp/btsEdDLxd2L/rVJOFRyuYSK9bKMmxuiXWK/img.png|CDM|1.3|{"originWidth":805,"originHeight":531,"style":"alignCenter","width":544,"height":359}_##]

CI/CD에 들어가기 전에 **DevOps**라는 개념에 대해서 알아보고자 합니다. DevOps는 Development + Operations의 줄임말으로, 소프트웨어 개발과 운영 팀 간의 협력, 개발과 배포 프로세스의 자동화, 지속적인 피드백과 지속적인 개선을 강조하는 문화와 철학을 나타냅니다. 주요 목표는 효율적이고 안정적인 소프트웨어 배포를 가능케하고, 협업을 강화해서 생산성과 서비스 안정성을 향상시키는 것입니다.

[##_Image|kage@llfFh/btsEaXxs9Vk/KtLUSzB3gl1GHItu7vUNr0/img.jpg|CDM|1.3|{"originWidth":750,"originHeight":500,"style":"alignCenter","width":429,"height":286}_##]

이러한 DevOps 문화는 2009년 'O'Relly Velocity Conference의 <하루에 10회 이상 배포하기: Filcker에서 Dev와 Ops의 협업>'에서 탄생했습니다

이러한 DevOps 문화가 생긴 이후 **CI/CD**라는 개념이 부각되었습니다. 조직들의 가장 큰 과제 중 하나는 시장 변화 및 고객 요구에 신속하고 유연하게 대응할 수 있는 개발안을 구축하는 것입니다. 이러한 문제에 대한 중추적인 솔루션인 Agile 문화와 DevOps의 한 부분으로써 CI/CD개념이 출현한 것 입니다. CI/CD는 빠르고 효율적이고 지속적으로 개발하기위한 DevOps 문화의 핵심적인 원칙을 구현하는 수단으로 나타냅니다.

## 2\. CI(Continuous Integration)

---

[##_Image|kage@etMRQU/btsD8xeOrq1/nRSklvD0iLq6Kek7Sv0k00/img.png|CDM|1.3|{"originWidth":704,"originHeight":358,"style":"alignCenter","width":549,"height":279}_##]

**CI(Continuous Integration)는 지속적 통합**이라는 의미를 가지고 있습니다. 개발자를 위한 자동화 프로세스인 지속적 통합으로 모든 개발이 끝난 이후에 코드 품질을 관리하는 고전적인 단점을 해소하기 위해 나타난 개념입니다. 코드 변경 사항이 정기적으로 빌드 및 테스트되어 (가능하면 매시간 또는 매일) 공유 리포지토리에 통합되는 과정을 통해 지속적으로 품질을 유지하면서 개발을 진행하는 방법입니다.

.CI의 프로세스를 살펴보면, 아래와 같습니다.

1\. 코드를 통합한다.(git으로 관리)

2\. 통합한 코드가 제대로 동작하는지 테스트 한다.

3\. 제대로 빌드가 되는지도 테스트한다.

4\. 결과를 정리하고 버그가 존재한다면 적어둔다.

CI는 CI서버를 통해서 위의 과정처럼 Git으로 관리되는 코드의 변경을 감지하고 자동으로 빌드와 테스트를 실행해줍니다.

만약 CI가 없다면 저러한 프로세스를 일일해 해주어야 할 것입니다. CI는 개발자에게 실시간으로 피드백을 실시간, 지속적으로 제공함으로써 개발자들은 품질을 확인하고 문제를 해결할 수 있습니다. 이를 통해 개발자들은 저 안정적인 환경에서 코드를 작성하고, 버그를 조기발견해서 소프트웨어의 품질을 향상시킬 수 있습니다.

## 3\. CD(Continuous Deployment/Deilvery)

---

[##_Image|kage@ckKMvX/btsEaOOaNER/VNrmhoLGEuZxxqucPxukrk/img.webp|CDM|1.3|{"originWidth":1024,"originHeight":473,"style":"alignCenter","width":687,"height":317}_##]

CD(Continuous Deployment,지속적 배포 )는 CI의 확장 개념으로, 소프트웨어가 항상 신뢰할 수 있는 수준에서 배포될 수 있도록 관리하자는 개념으로 지속적 제공(Continuous Delivery)로 사용되기도 합니다.

CI는 소스코드의 빌드와 테스트 병합까지 성공적으로 진행되었다면, 빌드와 테스트를 거쳐 github에 올라간 것을 의미합니다. CD는 성공적으로 병합된 내역을 저장소 뿐이 아니라 사용자가 사용할 수 있는 배포환경까지 릴리즈 하는 것을 의미합니다. 이는 소프트웨어를 빠르게 고객에게 제공하고 신속한 피드백을 통해 지속적인 개선을 가능하게 합니다.

## 4\. CI vs CD

---

[##_Image|kage@bin0E9/btsD8xMFBv2/fxr84415WwdtCHt6vzMo00/img.png|CDM|1.3|{"originWidth":1280,"originHeight":390,"style":"alignCenter","width":791,"height":241}_##]

Continuous Deployment(CD)와 Continuous Integration(CI)는 밀접한 관련이 있습니다. CI는 개발자들이 작성한 코드를 지속적으로 통합하여 빌드 및 테스트를 수행하는 것을 강조하는데, 이는 개발자들이 빈번한 코드 통합을 통해 코드 품질을 유지하고 안정적으로 동작하는지 확인할 수 있도록 돕습니다.

이를 통해 CI가 선행되어야 CD가 가능하다고 볼 수 있습니다. CI를 통해 소프트웨어의 품질이 유지되면서 신뢰성이 확보되기 때문에, CD를 통해 이러한 안정적인 소프트웨어를 지속적으로 프로덕션 환경에 배포할 수 있게 됩니다. 따라서 CI/CD라는 용어는 이 두 개념이 함께 작동하여 릴리스 주기를 단축하고 소프트웨어를 신속하게 제공할 수 있게 해주는 방법을 나타냅니다.

[##_Image|kage@HhUul/btsD4RY8xFa/KAVz1SXJk8zrW9eADl1Sy0/img.png|CDM|1.3|{"originWidth":632,"originHeight":462,"style":"alignCenter","width":466,"height":341}_##]

널리 사용되는 CI/CD 도구 중 하나인 Jenkins는 중앙 빌드 및 지속적인 통합 프로세스가 가능하며, Windows, macOS 및 기타 Unix 계열 운영 체제용 패키지가 포함된 독립형 Java 기반 프로그램입니다. 수백개의 플러그인을 사용할 수 있는 Jenkins는 소프트웨어 개발에서 CI를 구현하고, 빌드, 테스트, 배포 등의 자동화된 작업들을 지원하는 동시에 CD 파이프라인을 구축할 수 있는 강력한 플랫폼입니다.
