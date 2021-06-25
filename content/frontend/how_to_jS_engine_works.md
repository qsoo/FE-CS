## 자바스크립트 엔진이 코드를 실행하는 과정

🌱: 이해 못 한 부분

<br>

#### 학습 목표: 자바스크립트 엔진이 코드를 실행하는 과정을 알고 각 과정에 관여하는 작업들을 살펴보기



### 자바스크립트 엔진 동작 과정

<img src="how_to_JS_engine_works.assets/1_자바스크립트엔진작동과정.png">

<center>JS engine의 작동 과정</center>

<br>

자바스크립트 엔진의 동작 과정

1. Compiler optimization
2. Garbage collection
3. Hot code management
4. Caching
5. Other runtime aspects of the program

<br>

자바스크립트가 기기에서 로딩될 때 불러오고 파싱하고 그리고 스크립트 안의 코드를 실행한다. 자바스크립트 코드를 실행하는 것은 **자바스크립트 엔진**

<br>

자바스크립트 코드는 (컴파일러 툴체인에 전달되기 전에) AST로 변환된다

- AST(Abstract Syntax Tree)

  추상 구문 트리, 프로그래밍 언어로 작성된 소스 코드의 추상 구문 구조 트리

  추상적이라는 말에서 알 수 있다싶이 모든 정보를 담고 있는 것은 아니다

[AST test: astexplorer.net](https://astexplorer.net/)

<br>

컴파일 툴체인에선 1개 이상의 최적화 컴파일러를 통해 효율적인 `low-level-code`를 제공해준다

- low-level-code: 컴퓨터가 이해하기 쉽게 작성된 코드

  example: 기계어, 어셈블리어

<br>

자바스크립트 코드는 파서(ex. `acron`, `esprima`, `cheroot` ...)를 거쳐서 AST 표현식으로 변환된다

그리고 이 만들어진 AST는 인터프리터 실행의 첫 단계로 들어가게 된다.

- 인터프리터: 프로그래밍 언어의 소스 코드를 실행하는 환경

<br>

인터프리터는 AST를 `bytecode`로 변환시킨다.

- bytecode:
  - 특정 하드웨어가 아닌 가상 컴퓨터에서 돌아가는 실행 프로그램을 위한 이진 표현법
  - 보통 한 번에 하나의 명령어를 읽은 후 실행할 때 사용
  - 일반적으로 기계어보다 추상화

그 다음 반복되는 코드의 경우 `optimizing compiler`로 이동한다.

<br>

#### optimizing compiler

> `hot code`를 위해 최적화된 `machine level code`를 제공하는 역할

예를 들면 자바스크립트 컴파일러는 코드를 실행할 때 피드백을 실행하고 `Profileing data`를 모은다. 이 때 매번 동일한 유형의 매개 변수로 호출되고 여러 번 호출된 함수를 발견하면 optimizing compiler로 이동한다.

<br>

여기서 JS 엔진이 `hot code`라고 판단할 때만 최적화 컴파일러가 시작된다

- hot code: 자주 반복되어 수행되는 코드

<br>

### (추가할 사항)

🌱각 브라우저별 작동 과정

🌱각 단계별 세부사항 체크

<br>

### 참고 자료

[How the JavaScript engine works](https://javascript.plainenglish.io/js-engine-and-optimization-dac1f7fcb87d)

