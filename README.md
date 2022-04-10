# 코드 읽기

## 목표

## 무엇을 읽을까?
- 여러분이 의존하는 코드를 읽어라: 이미 사용 중인 라이브러리나 플러그인으로 시작하자. 예로 워드프레스 플러그인, 루비 젬, jQuery 플러그인을 고려해보자.
- 감명 깊은 소프트웨어 코드를 읽어라: 오픈소스 프로젝트 중에서 아키텍처가 잘 잡혀 있고 문서화가 잘 된 코드부터 시작하면 된다(B급 프로그래머: 스프링 소스 코드 일부를 읽어보고 사용자(개발자!)를 배려하는 치밀함에 정말 놀란 적이 있다.
- 존경하는 사람이 만든 소프트웨어 코드를 읽어라: 오픈소스를 이끄는 사람 중에서 존경하는 개발자가 있다면 거기서 출발하자(B급 프로그래머: 클린코드에서 작성한 로버트 C. 마틴이 작성한 코드 사례를 추천한다).
- 실제 다룰 수 있는 코드를 읽어라: 처음부터 너무 욕심내어 대규모 프로젝트를 구성하는 코드를 읽으면 혼란에 빠진다. 전체 논리를 한 번에 머리에 넣을 수 있는 작은 프로젝트부터 읽어보자(B급 프로그래머: 되도록 초기 버전을 권장한다. 버전이 올라갈수록 복잡도는 기하급수적으로 증가하기 때문이다. 피보탈에서 만든 Cloud Foundry도 초기 버전은 정말 읽고 이해할만 했다. 이 코드 덕분에 루비 실전 기술을 몇 가지 배웠다.).
## 어떻게 읽을까?
- 큰 그림을 보자: 개별 단위 함수부터 파고드는 대신 웹 사이트, 튜토리얼, 문서, 코드 이외 다른 참고 자료부터 살펴보자. 프로젝트 구조 파악이 우선이다. 코드 계층 구조를 파악하고 어떤 코드가 어떤 코드를 import 하는지, namespace는 어떻게 명명되어 있는지를 살펴보자(B급 프로그래머: 코드 내부에서 함수는 헤더 파일에 대한 교차 참조를 걸어주는 여러 가지 도구를 사용하면 시간을 절약할 수 있다).
- 찾아낸 사실을 문서로 만들자: 코드 읽기는 수동적인 활동이 아니다. 찾아낸 사실을 문서로 만들고 프로그램 흐름에 맞춰 가정과 결론을 나중에 찾아볼 수 있게 주석으로 달아놓자.
- 테스트를 사용하라 루크!: 아마도 테스트 코드가 프로젝트 내에 포함되어 있을 것이다. 테스트는 출발점으로 아주 좋다. 코드가 어떻게 동작하고 어떤 가정을 내포하는지를 설명하기 때문이다. 실제로 코드 읽기에 앞서 테스트를 돌려서 환경이 제대로 구성되어 있는지 확인할 필요가 있다(B급 프로그래머: 테스트에 앞서 일단 빌드부터 성공해야 한다. 컴파일 언어에 대한 환경 구성이 확실히 어렵긴 하지만 스크립트 언어인 경우에도 의존성 맞추느라 고생할 가능성이 상당히 높다. 충격에 대비하라!).
- 실행하고, 변경하고, 다시 실행하자: 일단 모든 것을 분해했다 다시 조립하면서 이해도를 높이자. 정말 멋진 기능을 하나 추가해서 테스트가 통과하는지 살펴보자. 다양한 코드 상태를 확인할 수 있게 로그 수준을 높여보자(B급 프로그래머: 이 과정에서 디버거를 사용해 흥미로운 부분에 중단점을 걸어 내부 상태를 파악하기도 한다).
## 어디서 시작할까? 
- 깃허브와 같은 공개 소스코드 저장소에서 출발하자. git clone 만으로 손쉽게 코드를 복제해서 시작할 수 있다.
