# 20220411

## 코드 읽는 방법

### 코드실행
  - 첫번째 단계. 프로젝트를 빌드하고 실행하는 방법 익히기
  - 특정 프로젝트에서 사용하는 모든 타사 라이브러리와 의존하는 특정 프레임워크등에 대한 명확한 그림을 얻을 수 있음
  - 유사한 프로젝트 작성시 아이디어 얻기 좋아진다
### 상위 수준 논리 찾기
  - 프로젝트 읽기 시작할 때 각 세부 사항으로 건너뛰지 않을 수 있음
  - 구조에 집중
  - 비지니스 로직이 있는 위치, UI코드가 보관되어 있는 위치, 컨트롤러가 있는 위치등과 같은 다양한 패키지 부터 시작
  - 전체 프로젝트를 흟어 보고 기본 아이디어를 얻어서 진행
  - 초점을 맞추고 싶은 부분과 가장 먼저 읽고 싶은 부분을 스스로 결정
### 도구 사용
  - 단축기, 약어 익히기
### 언어/관례 알기
  - 고유한 규칙, 스타일, 구문집합 등을 알게 되면 식별하고 능력 향상 시키는데 도움이 됨
### 모범사례/디자인 패턴 읽기
  - 코드 또는 코드의 특정 구성이 모호하거나 익숙하지 않을 수 있음
  - ex) 생성자가 비공개로 유지되는 Singleton패턴 : 실제 사용 사례가 많은 클래스를 두번 이상 인스턴스화 하는것을 방지..
### 코드 검토

### 코드에 자유롭게 주석 달기
  - 자신의 코드에도 "사용된 표준, 핵심구조, 사용된 논리, clean한지.."등 작성
### 임시 리팩토링
  - 긴 메서드를 사용하지 시작한 다음 메서드를 여러 조각으로 계속 나눌 수 있음
  - 더 큰 방법 뒤에 숨겨진 의도가 무었인지 이해할 때까지 계속 하기
  - 메서드가 수행하는 작업에 대해 몇가지 메모한 다음 변경 사항을 롤백
