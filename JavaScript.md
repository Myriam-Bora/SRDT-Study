
------

# 04 변수


## 4.1 변수란 무엇인가? 왜 필요한가?

<u>***변수 : 하나의 값을 저장하기 위해 확보한 메모리 공간을 식별하기 위해 붙인 이름***</u>. **

- 다음과 같은 자바스크립트 코드를 실행하면 컴퓨터에서 어떤 일이 일어나는가?

```javascript
10 + 20
```

- 자바스크립트 엔진이 10 + 20 이라는 식의 의미를 해석하면 +연산을 수행하기 의해 좌변과 우변의 피연산자를 기억한다

- ***<u>컴퓨터는 CPU를 사용해 연산하고</u>***
- ***<u>메모리 : 데이터를 저장할 수 있는 메모리 셀의 집합체</u>***
- 메모리를 사용해 데이터를 기억한다
- 메모리 셀 하나의 크기는 1바이트(8비트)
- 컴퓨터는 1바이트 단위로 데이터를 저장하거나 읽어 들인다
- 셀은 고유의 메모리 주소 (메모리 공간의 위치)를 나타내며 0부터 메모리 크기만큼 정수로 표현된다
- 컴퓨터는 모든 데이터를 종류(숫자,텍스트,이미지,동영상 등)와 상관 없이 모두 2진수로 처리한다 
- CPU의 연산이 끝나고 연산결과를 메모리에 저장해도 만들어낸 숫자 값 30을 재사용할 수는 없다
- 메모리 주소를 통해 값이 있는 메모리 공간에 직접 접근하는 것은 치명적 오류를 발생시킬 가능성이 높기 때문
- 프로그래밍 언어는 기억하고 싶은 값을 메모리에 저장하고 저장된 값을 읽어 들여 재사용하기 위해 변수라는 메커니즘을 제공한다
- ***<u>즉, 값의 위치를 가리키는 상직적인 이름</u>***
- 따라서 개발자가 직접 메모리 주소를 통해 값을 저장하고 참조할 필요가 없고 변수를 통해 안전하게 값에 접근한다

```javascript
var result = 10 + 20;
```

- <u>***변수이름***</u> (위 예제에서는 result) : 메모리 공간에 저장된 값 30을 다시 읽어 들여 재사용할 수 있도록 값이 저장된 메모리 공간에 상징적인 이름을 붙인 것

- ***<u>변수 값</u>*** : 변수에 저장된 값 (위 예제에서는 30)

- ***<u>할당</u>*** : 변수에 값을 저장 (=대입 , 저장)

- ***<u>참조</u>*** : 변수에 저장된 값을 읽어 들이는 것

------


## 4.2 식별자

- ***<u>식별자</u>*** : 변수 이름. 어떤 값을 구별해서 식별할 수 있는 고유한 이름
  - 값이 아니라 어떤 값이 저장되어 있는 메모리 주소를 저장한다
  - 즉, 값이 저장되어 있는 메모리 주소와 매핑관계를 맺으며, 메모리 주소에 붙인 이름이다

------

## 4.3 변수 선언

- ***<u>변수 선언</u>*** : 변수를 생성 하는 것
- 값을 저장하기 위한 메모리 공간을 확보
- 변수 이름과 확보된 메모리 공간의 주소를 연결해서 값을 저장할 수 있게 준비하는 것
- var, let, const 키워드를 사용한다
- ***<u>키워드</u>***  : 자바스크립트 엔진이 수행할 동작은 규정한 명령어. 예를 들어, var 키워드를 만나면 뒤에 오는 변수 이름으로 새로운 변수를 선언한다
- 다음 코드는 var 키워드 뒤에 오는 변수 이름으로 새로운 변수를 선언할 것을 지시하는 키워드이다

```javascript
var score;
```

- 변수를 선언한 이후 아직 변수에 값을 할당하지 않았기 때문에 확보된 메모리 공간은 ***undefined*** 라는 값이 암묵적으로 할당되어 초기화 된다

- ***<u>초기화</u>*** : 변수가 선언된 이후 최초로 값을 할당 하는 것

  

------

## 4.4 변수 선언의 실행 시점과 변수 호이스팅

- ***<u>호이스팅</u>*** : 변수 선언문이 코드의 선두로 끌어 올려진 것처럼 동작하는 것

```javascript
console.log(score);   //undefined
var score;
```

- 위 코드는 순차적으로 실행된다면 console.log가 실행되는 시점에 아직 변수가 선언되기 이전이므로 ReferenceError가 발생해야 하지만 undefined가 출력된다
- 자바스크립트 엔진은 소스코드를 한 줄씩 순차적으로 실행하기 전에 ***소스코드 평가 과정***(23장 실행 컨텍스트 참고)을 거친다
- 소스코드 평가 과정은 모든 선언문(변수,함수 등)을 찾아내어 먼저 실행한다
- 소스코드 평가 과정이 끝나면 선언문을 제외한 소스코드를 순차적으로 실행한다


------

## 4.5 값의 할당

- 변수 선언과 값의 할당을 하나의 문으로 단축 표현할 수 있다

```javascript
var score = 80;
```

- **주의** 변수 선언은 소스코드가 순차적으로 실행되는 런타임 이전에 먼저 실행, 값의 할당은 런터임에 실행 된다.

```javascript
console.log(score); //undefined
var score; 		// (1)변수선언
score = 80;      // (2)값의 할당
console.log(score); //80
```

- (1) 변수선언은 런타임 이전에 먼저 실행되기 때문에 (2)시점에는 이미 변수 선언이 완료된 상태이다.

  

------

## 4.6 값의 재할당

- ***<u>재할당</u>***  : 이미 값이 할당되어 있는 변수에 새로운 값을 또다시 할당하는 것

```javascript
var score = 80;  //변수 선언과 값의 할당
score = 90;      // 값의 재할당
```

- 이전 값 80이 저장되어 있던 메모리 공간을 지우고 그 메모리공간에 재할당 값 90을 새롭게 저장하는 것이 아니라 

  **새로운 메모리 공간을 확보하고 그 메모리 공간에 숫자 값 90을 저장한다**

- 현재 score 변수의 값은 90이고, 이전 값은 undefined와 80은 어떤 식별자와도 연결 되어 있지 않다

- 이런 불필요한 값들은 가비지 콜렉터에 의해 메모리에서 자동 해제 된다. 단, 언제 해제될지는 예측할 수 없다

------


## 4.7 식별자 네이밍 규칙

- 네이밍 컨벤션 : 하나 이상의 영어 단어로 구성된 식별자를 만들 때 가독성 좋게 단어를 한눈에 구분하기 위해 규정한 명명 규칙

```javascript
var firstName;//카멜 케이스
var first_name; //스네이크 케이스
var FirstName; //파스칼 케이스

//헝가리언 케이스
var strFirstName; //type + identifier
var $elem = document.getElementById('myId');  //DOM 노드
var observable$ = fromEvent(document, 'click'); //RxJS 옵저버블
```

- 자바스크립트에서는 일반적으로 변수, 함수 이름에는 카멜 케이스 사용
- 생성자 함수, 클래스 이름에는 파스칼 케이스 사용
- ECMAScript 사양에 정의되어 있는 객체,함수 : 카멜,파스칼 케이스


------

# 05 표현식과 문

## 5.1 값

- ***<u>값</u>*** : 식(표현식)이 평가되어 생성된 결과

------

## 5.2 리터럴

- ***<u>리터럴</u>*** : 사람이 이해할 수 있는 문자 또는 약속된 기호를 사용해 값을 생성하는 표기법

```javascript
3
```

- 위 예시의 3은 단순한 아라비아 숫자가 아니라 사람이 이해할 수 있는 숫자 리터럴이다
- 자바스크립트 엔진은 코드가 실행되는 시점인 런타임에 리터럴을 평가해 값을 생성한다

------

## 5.3 표현식

- <u>***표현식***</u> : 값으로 평가될 수 있는 문. 표현식이 평가되면 새로운 값을 생성하거나 기존값을 참조한다
- 리터럴은 값으로 평가된다, 즉 리터럴도 표현식이다

```javascript
var score = 100;  //리터럴 : 100
```

```javascript
var score = 50 + 50; //리터럴과 연산자로 이뤄져 있다. 숫자 값 100을 생성하므로 표현식이다.
score;  // 100  -> 변수 식별자를 참조하면 변수 값으로 평가. 값을 생성하진 않지만 값으로 평가되므로 표현식이다.
```

- 표현식은 리터럴,식별자(함수,함수 등의 이름),연산자, 함수 호출 등의 조합으로 이뤄질 수 있다
- 즉, ***값으로 평가될 수 있는 문은 모두 표현식이다***

------

## 5.4 문

- ***<u>문</u>*** : 프로그램을 구성하는 기본 단위이자 최소 실행 단위. 명령문이라도 부른다
- 문의 집합으로 이뤄진 것이 프로그램이며, 문을 작성하고 순서에 맞게 나열하는 것이 프로그래밍이다
- 문은 여러 토큰으로 구성된다
- ***<u>토큰</u>*** : 문법적인 의미를 가지며, 문법적으로 더 이상 나눌 수 없는 코드의 기본 요소
- 예를 들어, 키워드, 식별자, 연산자, 리터럴, 세미콜론,마침표 등의 특수기호는 문법적인 의미를 가지며 문법적으로 더 이상 나눌 수 없는 코드의 기본 요소이므로 모두 토큰이다.
- 문은 선언문,할당문,조건문,반복문 등을 구분 할 수 있다

```javascript
//변수 선언문
var x;

//할당문
x = 5;

//함수 선언문
function foo () {}

//조건문
if (x > 1) {console.log(x);}

//반복문
for(var i = 0 ; i < 2; i++){console.log(i);}
```



------

## 5.5 세미콜론과 세미콜론 자동 삽입 기능

- ***<u>세미콜론</u>*** : 문의 종료를 나타낸다. 
- 자바스크립트 엔진은 세미콜론으로 문이 중료한 위치를 하악하고 순차적으로 하나씩 문을 실행한다
- 단, 0개 이상의 문을 중괄호로 묶은 코드 블록 ({...}) 뒤에는 세미콜론을 붙이지 않는다(if문,for문,함수 등)
- 이러한 코드 블록은 언제나 문의 종료를 의미하는 자체 종결성을 갖기 때문
- 문의 끝에 붙이는 세미콜론은 생략이 가능한데, 자바스크립트 엔진이 소스코드를 해석할 때 문의 끝이라고 예측되는 지점에 세미콜론을 자동으로 붙여주는 자동 삽입 기능이 암묵적으로 수행되기 때문
- 하지만, 이런 동작이 개발자 예측과 일치하지 않는 경우가 있다

```javascript
var bar = function (){}
(function() {})();

//자동삽입기능 동작 결과 -> var bar = function(){} (function(){})();
//개발자의 예측         -> var bar = function(){}; (function(){})();
//Uncaught TypeError: (intermediate value)(...) is not a function
```

------

## 5.6 표현식인 문과 표현식이 아닌 문

- ***표현식인 문과 표현식이 아닌 문을 구별하는 가장 간단한 방법은 변수에 할당해 보는 것***
- 표현식인 문은 값으로 평가되므로 변수에 할당할 수 있다
- 표현식이 아닌 문은 값으로 평가할 수 없으므로 변수에 할당하면 에러가 발생한다

```javascript
//변수 선언문은 표현식이 아닌 문이다
var x;

//할당문은 그 자체가 표현식이지만 완전한 문이기도 하다. 즉, 할당문은 표현식인 문이다
x = 100;


//표현식이 아닌 문은 값처럼 사용할 수 없다
var foo = var x; //SysntaxError : unexpected token var

//표현식인 문은 값처럼 사용할 수 있다
var foo = x = 100;
console.log(foo); //100
```

- 크롬 개발자 도구에서 표현식이 아닌 문을 실행하면 언제나 undefined를 출력한다. 이를 완료값이라 한다








------

# 07 연산자 (Operator)



## 7.1 산술 연산자

- 수학적 계산을 수행해 새로운 숫자 값을 만든다

- *<u>**부수효과**</u>* : 피연산자의 값을 변경

  

### <u>7.1.1 이항 산술 연산자</u>

- 모든 이항 산술 연산자에는 부수 효과가 없다

- | 이항 산술 연산자 |  의미  | 예시         |
  | :--------------: | :----: | ------------ |
  |        +         |  덧셈  | `5+2; //7`   |
  |        -         |  뺄셈  | `5-2; //3`   |
  |        *         |  곱셈  | `5*2; //10`  |
  |        /         | 나눗셈 | `5/2; //2.5` |
  |        %         | 나머지 | `5%2; //1`   |



### <u>7.1.2 단항 산술 연산자</u>

- | 단항 산술 연산자 |                       의미                        | 부수효과 |
  | :--------------: | :-----------------------------------------------: | :------: |
  |        ++        |                       증가                        |    O     |
  |        --        |                       감소                        |    O     |
  |        +         |                어떠한 효과도 없다                 |    X     |
  |        -         | 양수를 음수로, 음수를 양수로 반전한 값을 반환한다 |    X     |

- 증가/감소( ++ / - - ) 연산자는 위치에 따라 차이가 있다

 ```javascript
    var x = 5;
    
    var result;
    
    result = x++; *//5 6 : 선할당 후증가*
    
    result = ++x; *//7 7 : 선증가 후할당*
 ```

- 숫자 타입이 아닌 피연산자에 + 단항 연산자를 사용하면 피연산자를 숫자 타입으로 변환하여 반환한다.

 ```javascript
var x = "5";

console.log(+x); // 1  : 문자열을 숫자로 타입 변환한다

console.log(x); // "1" : 부수 효과는 없다

var y = true;

console.log(+x); *// 1  : 불리언 값을 숫자로 타입 변환한다*

var y = "hello";

console.log(+x); *//NaN : 문자열을 숫자로 타입 변환할 수 없다*
 ```

  

### <u>7.1.3 문자열 연결 연산자</u>

- 연산자 + 는 피연산자 중 하나 이상이 문자열인 경우 문자열 연결 연산자로 동작 한다. 그 외의 경우는 산술 연산자로 동작한다

  `console.log("1" + 2); *// '12' : 문자열 연결 연산자*`

  `console.log(1 + "2"); *// '12' : 문자열 연결 연산자*`

  

  `console.log(1 + true); *// 2  : true는 1로 타입 변환된다*`

  `console.log(1 + false); *// 1  : false는 0로 타입 변환된다*`

  `console.log(1 + null); *// 1  : null는 0로 타입 변환된다*`

  `console.log(1 + undefined); *// Nan : undefined 는 숫자로 타입 변환 되지 않는다*`

- ***<u>암묵적 타입 변환</u>*** : 개발자의 의도와 상관없이 자바스크립트 엔진에 의해 타입이 자동 변환 되는 것

  - 위에 예제에서 1 + true를 연산하면 불리언 타입의 값인 true를 숫자 타입은 1로 강제로 변환 후 연산

    

------



## 7.2 할당 연산자

- 우항에 있는 피연산자의 평가 결과를 좌항에 있는 변수에 할당한다

- | 할당 연산자 |   예   | 동일 표현 | 부수 효과 |
  | :---------: | :----: | :-------: | :-------: |
  |      =      | x = 5  |   x = 5   |     O     |
  |     +=      | x += 5 | x = x + 5 |     O     |
  |     -=      | x -= 5 | x = x - 5 |     O     |
  |     *=      | x *= 5 | x = x * 5 |     O     |
  |     /=      | x /= 5 | x = x / 5 |     O     |
  |     %=      | x %= 5 | x = x % 5 |     O     |



------



## 7.3 비교 연산자

- 좌항과 우항의 피연산자를 비교한 다음 그 결과를 불리언 값으로 반환한다

  

### 7.3.1 동등/일치 비교 연산자

- 좌항과 우항의 피연산자가 같은 값으로 평가되는지 비교해 불리언 값을 반환한다
- 동등 비교 연산자는 느슨한 비교를 , 일치 비교 연산자는 엄격한 비교를 한다

| 비교 연산자 |  사례   |            설명            | 부수 효과 |
| :---------: | :-----: | :------------------------: | :-------: |
|     ==      | x == y  |      x와 y 값이 같다       |     X     |
|     !=      | x != y  |      x와 y값이 다르다      |     X     |
|     ===     | x === y |  x와 y의 값과 타입이 같다  |     X     |
|     !==     | x !== y | x와 y의 값과 타입이 다르다 |     X     |

- 동등 비교 연산자는 암묵적 타입 변환을 통해 타입을 일치 시킨 후 같은 값인지 비교 한다

  `console.log(5 == "5"); *// true : 타입은 다르더라도 암묵적 타입 변환 후 같은 값이면 true*`

- 일치 비교 연산자는 좌항과 우항의 피연산자가 타입과 값이 같은 경우에만 true를 반환한다

  `console.log(5 === "5"); *// false*`

- 숫자가 NaN인지 조사하려면 빌트인 함수 isNaN을 사용해야 한다

  `console.log(NaN === NaN); *// false  : NaN은 자신과 일치하지 않는 유일한 값이다*`

  `console.log(isNaN(NaN)); *// true  : isNaN함수는 지정한 값이 NaN인지 확인하고 불리언 값으로 반환*`

  `console.log(isNaN(10)); *// false  : isNaN함수는 지정한 값이 NaN인지 확인하고 불리언 값으로 반환*`

- 양의0과 음의 0 을 비교하면 true를 반환한다. 주의 할 것

  `console.log(0 === -0); *// true*`

  `console.log(0 == -0); *// true*`

- Object.js 메소드는 위 NaN과 +0 -0의 문제를 해결하고, 일치 비교 연산자(===)와 동일하게 동작한다

  `console.log(Object.is(+0, -0));  *// false*`

  `console.log(Object.is(NaN, NaN)); *// true*`

  

### <u>7.3.2 대소 관계 비교 연산자</u>

- 피연산자의 크기를 비교하여 불리언 값을 반환한다

- | 대소 관계 비교 연산자 |  예제  | 부수 효과 |
  | :-------------------: | :----: | :-------: |
  |           >           | x > y  |     X     |
  |           <           | x < y  |     X     |
  |          >=           | x >= y |     X     |
  |          <=           | x <= y |     X     |



------



## 7.4 삼항 조건 연산자

- 조건식의 평가 결과에 따라 반환할 값을 결정한다.

- 부수 효과는 없다

- 첫 번째 피연산자가 true이면 두 번째 피연산자를 반환 , false로 평가되면 세 번째 피연산자를 반환한다

  `var x = 2;`

  `var result = x % 2 ? '홀수' : '짝수';`

  `console.log(result);  *//짝수  : 2 % 2는 0이므로 false로 암묵적 타입 변환한다*`

- if ...else 와 유사하지만 if...else는 표현식이 아닌 "문"이기 때문에 값처럼 사용할 수 없다

  `var x = 10;`

  `var result = if(x % 2) {result='홀수'} else {result='짝수';};  *//SyntaxError: Unexpected token if*`

- 삼항 조건 연산자 표현식은 값으로 평가할 수 있는 표현식인 문이다.

- 하지만 조건에 따라 수행해야 할 문이 하나가 아니라 여러 개라면 if...else 문의 가독성이 더 좋다

  

------



## 7.5 논리 연산자

- 우항과 좌항의 피연산자를 논리 연산한다

  | 논리 연산자 |    의미     | 부수 효과 |
  | :---------: | :---------: | :-------: |
  |    \|\|     | 논리합(OR)  |     X     |
  |     &&      | 논리곱(AND) |     X     |
  |      !      |  부정(NOT)  |     X     |

- 논이 부정(!) 연산자는 언제나 불리언 값을 반환한다

- 만약 피연산자가 불리언 값이 아니면 불리언 타입으로 암묵적 타입 변환된다

  `console.log(!0);    *//true*`

  `console.log(!"Hello"); *//false*`

- 논리합 (||) 또는 논리곱(&&) 연산자 표현식의 평과 결과는 불리언 값이 아닐 수도 있다. 언제나 2개의 피연산자 중 어느 한쪽으로 평가 된다

  `console.log("cat" && "dog"); *//dog*`

  

------



## 7.6 쉼표 연산자

- 쉼표(,) 연산자는 왼쪽 피연산자부터 차례대로 피연산자를 평가하고 마지막 피연산자의 평가가 끝나면 마지막 피연산자의 평가 결과를 반환한다

  `var x,y,z;`

  `x=1,y=2,z=3; *//3*`



------



## 7.7 그룹 연산자

- 소괄호 '( )' 로 피연산자를 감싸는 그룹 연산자는 자신의 피연산자인 표현식을 가장 먼저 평가한다.
- 그룹 연산자는 연산자 우선순위가 가장 높다



------



## 7.8 typeof 연산자

- 피연산자의 데이터 타입을 문자열로 반환한다

- "null" 을 반환하는 경우는 없기 때문에 7개의 데이터 타입과 정확히 일치하지는 않다

  `console.log(typeof '');     *//"string"*`

  `console.log(typeof 1);     *//"number"*`

  `console.log(typeof NaN);    *//"number"*`

  `console.log(typeof true);    *//"boolean"*`

  `console.log(typeof undefined); *//"undefined"*`

  `console.log(typeof Symbol() );  *//"sysmbol"*`

  `console.log(typeof function(){}); *//"function"*`

  `console.log(typeof null);    *//"object"  : 주의!*`

  `console.log(typeof []);     *//"object"  : 주의!*`

  `console.log(typeof {});     *//"object"  : 주의!*`

- 따라서 값이 null 타입인지 확인할 때는 일치 연산자(===)를 사용한다



------



## 7.9 지수 연산자

- ES7에서 도입. 좌항의 피연산자를 밑(base)으로, 우항의 피연산자를 지수(exponent)로 거듭 제곱하여 숫자 값을 반환한다

  `console.log(2 ** 2);     *//4*`

  `console.log(2 ** 2.5);    *//5.65685424949238*`

- 음수를 거듭제곱의 밑으로 사용해 계산하려면 괄호로 묶어야 한다

  `console.log((-5) ** 2); *//25*`

- 지수 연산자는 이상 연산자 중에서 우선순위가 가장 높다

  `console.log(2 * 5 ** 2); *//50*`

  

------



## 7.12 연산자 우선 순위

- 우선순위를 그룹 연산자를 이용하여 명시적으로 저절하는 것을 권장 한다

| 우선순위 | 연산자                                                       |
| -------- | ------------------------------------------------------------ |
| 1        | ( )                                                          |
| 2        | new(매개변수 존재) ,  [ ]프로퍼티 접근, ( ) 함수호출 , ?. (옵셔널 체이닝 연산자) |
| 3        | new(매개변수 미존재)                                         |
| 4        | x++ , x--                                                    |
| 5        | !x , +x , -x , ++x , --x , typeof , delete                   |
| 6        | ** (이항 연산자 중에서 우선순위가 가장 높다)                 |
| 7        | * , / , %                                                    |
| 8        | + , -                                                        |
| 9        | < , <= , > , >= , in , instanceof                            |
| 10       | == , !=, ===, !==                                            |
| 11       | ?? (null 병합 연산자)                                        |
| 12       | &&                                                           |
| 13       | \|\|                                                         |
| 14       | ? ... : ... (삼항 연산자)                                    |
| 15       | 할당 연산자 (=,+=,-=,...)                                    |
| 16       | ,                                                            |



------

## 7.13 연산자 결합 순서

- 연산자의 어느쪽부터 평가를 수행할 것인지를 나타내는 순서

- | 결합 순서    | 연산자                                                      |
  | ------------ | ----------------------------------------------------------- |
  | 좌항 -> 우항 | + - / % < <= > >= && \|\| . [ ] ( ) ?? ? in instanceof      |
  | 우항 -> 좌항 | ++ -- 할당연산자 !x +x -x ++x --x tyoeof delete ? ... : ... |



------

# 09 타입 변환과 단축 평가



## 9.1 타입 변환이란?

- 명시적 타입 변환 (=타입 캐스팅) : 개발자가 의도적으로 값의 타입을 변환
- 암묵적 타입 변환 (=타입 강제 변환) : 개발자의 의도와는 상관없이 자바스크립트 엔진에 의해 암묵적으로 타입이 자동 변환



------

## 9.2 암묵적 타입 변환



### **<u>9.2.1 문자열 타입으로 변환</u>**

- +연산자는 피연산자 중 하나 이상이 문자열이면 문자열 연결 연산자로 동작한다.

- 즉, 피연산자 중에서 문자열 타입이 아닌 피연산자를 문자열 타입으로 암묵적 타입 변환한다

  `console.log(1 + "12"); *// "112" *`



### **<u>9.2.2 숫자 타입으로 변환</u>**

- 산술 연산자의 피연산자는 모두 숫자 타입으로 암묵적 타입 변환 한다

- 숫자 타입으로 변환할 수 없는 경우는 산술 연산을 수행할 수 없으므로 표현식의 평가 결과는 NaN이 된다

  `console.log(1 - "1"); *// 0*`

- 비교 연산자는 피연산자의 크기를 비교하므로 코드 문맥상 모두 숫자 타입이여야 한다.

- 자바스크립트 엔진은 비교 연산자의 피연산자 중에서 숫자 타입이 아닌 피연산자를 숫자 타입으로 암묵적 타입 변환한다

- +단항 연산자는 피션안자가 숫자 타입이 아니면 숫자 타입의 값으로 암묵적 타입 변환 한다 

  (주의 : 이항 이상은 문자열로 변환된다)

  `console.log(+"0");   *// 0*`

  `console.log(+"string"); *// Nan*`

- 빈 문자열(" "), 빈 배열([ ]), null, false는 0, true는 1

  `console.log(+"");    *// 0*`

  `console.log(+null); *// 0*`

  `console.log(+[]); *// 빈 배열 : 0*`

- 객체와 빈 배열이 아닌 배열, undefined 는 변환 되지 않아 NaN

  `console.log(+undefined); *// NaN*`

  `console.log(+{}); *// 객체 : NaN*`

  `console.log(+[10, 20]); *// 배열 : NaN*`

  `console.log(+function () {}); *// NaN*`



### 9.2.3 불리언 타입으로 변환

- if문,for문과 같은 제어문,조건식은 불리언으로 평가 되어야 하는 표현식이다. 

- 따라서 조건식의 평가 결과를 불리언 타입으로 암묵적 타입 변환 한다

- 이때 자바스크립트 엔진은 불리언 타입이 아닌 값을 Truthy(참으로 평가되는 값) 또는 Falsy(거짓으로 평가되는 값) 으로 암묵적 타입 변환 한다

- false 로 평가되는 Falsy 값

  > false 
  >
  > undefined
  >
  > null
  >
  > 0 , -0
  >
  > NaN
  >
  > ' '  (빈 문자열)

- Falsy 값 외의 모든 값은 true로 평가 된다



------

## 9.3 명시적 타입 변환


### 9.3.1 문자열 타입으로 변환

- String 생성자 함수를 new 연산자 없이 호출

  `console.log(String(NaN)); *// "NaN"*`

  `console.log(String(true)); *// "true"*`

- Object.prototype.toString 메서드 사용

  `console.log(NaN.toString()); *// "NaN"*`

  `console.log(true.toString()); *// "true"*`

- 문자열 연결 연산자 이용

  `console.log(NaN + ""); *// "NaN"*`

  `console.log(true + ""); *// "true"*`



### **<u>9.3.2 숫자 타입으로 변환</u>**

- Number 생성자 함수를 new 연산자 없이 호출

  `console.log(Number("0")); *// 0*`

  `console.log(Number(true)); *// 1*`

- parseInt , parseFloat 함수를 사용 (문자열만 변환가능)

  `console.log(parseInt("0")); *// 0*`

  `console.log(parseFloat("10.53")); *// 10.53*`

- +단항 산술 연산자 이용 (주의 : 이항 이상은 문자열로 변환된다)

  `console.log(+"0"); *// 0*`

- *산술 연산자 이용

  `console.log("10.53" * 2); *// 21.06*`

  `console.log(true * 2); *// 2*`



### **<u>9.3.3 불리언 타입으로 변환</u>**

- Boolean 생성자 함수를 new 연산자 없이 호출

  `console.log(Boolean("")); *// false*`

  `console.log(Boolean(1)); *// true*`

- ! 부정 논리 연산자를 두 번 사용

  `console.log(!!""); *// false*`

  `console.log(!!1); *// true*`

  

------

## 9.4 단축 평가



### **<u>9.4.1 논리 연산자를 사용한 단축 평가</u>**

- 논리곱(&&) 연산자는 두 개의 피연산자가 모두 true로 평가 될 때 true로 반환한다

- 논리곱 연산자는 좌항에서 우항으로 평가 진행된다

- 이때 논리곱 연산자는 논리 연산의 결과를 결정하는 두 번째 피연산자를 그대로 반환한다

  `console.log("Cat" && "Dog"); *// "Dog"*`

- 논리합( || ) 도 논리곱 연산자와 동일하게 동작한다

- 단, 위 예시에서 피연산자 'Cat' 은 true 이므로 두 번째 피연산자까지 평가해 보지 않아도 평가할 수 있다

- 이때 논리합 연산자는 논리연산의 결과를 결정한 첫 번째 피연산자 'Cat'을 반환한다

- ***<u>단축평가</u>*** : 논리 연산의 결과를 결정하는 피연산자를 타입 변환하지 않고 그대로 반환. 표현식을 평가하는 도중에 평가 결과가 확정된 경우 나머지 평가 과정을 생략한다

- 단축 평가 규칙

  |  단축 평가 표현식   | 평가 결과 |
  | :-----------------: | :-------: |
  | true \|\| anything  |   true    |
  | false \|\| anything | anything  |
  |  true && anything   | anything  |
  |  false && anything  |   false   |

- 단축 평가를 이용하여 if문을 대체 할 수 있다

```javascript
var done = true;

var message = '';

*//다음 두줄은 같은 문장이다 : done이 true이면 message에 '완료'를 할당한다*

*if*(done) message='완료'

message = done && '완료';
```

- 조건이 false 일 때 무언가를 해야한다면 논리합 연산자 표현식으로 if문을 대체할 수 있다

 ```javascript
var done = false;

var message = '';

*//다음 두줄은 같은 문장이다 : done이 false이면 message에 '미완료'를 할당한다*

*if*(!done) message='미완료'

message = done || '미완료';
 ```

- 삼항 조건 연산자도 if..else 문을 대체할 수 있다

```javascript
var done = true;

var message = "";

*//다음 두 문장은 똑같이 작동한다*

*if* (done) message = "완료";

*else* message = "미완료";

console.log(message); *//완료*

message = done ? "완료" : "미완료";

console.log(message); *//완료*

```



### **<u>9.4.2 옵셔널 체이닝 연산자</u>**

- *<u>**옵셔널 체이닝 연산자**</u>*  (?. ) : 좌항의 피연산자가 null 또는 undefined인 경우 undefined를 반환하고, 그렇지 않으면 우항의 프로퍼티 참조를 이어간다

- 객체를 가리키기를 기대하는 변수가 null 또는 indefined가 아닌가 확인하고 프로퍼티를 참조할 때 유용하다

 ```javascript
 var elem = null;

*//elem이 null 또는 undefined이면 undefined를 반환하고,*

*//그렇지 않으면 우항의 프로퍼티 참조를 이어간다*

var value = elem?.value;

console.log(value); *//undefined* 
 ```

- 옵셔널 체이닝 연산자가 도입되지 이전에는 논리연산자(&&)를 사용하였지만 좌항 피연산자가 0 이나 ' ' 인 경우 문제가 생긴다

 ```javascript
 var str = '';

var length = str && str.length; //str가 false 이므로 str을 반환한다 

console.log(length); *// ''  : 문자열의 길이를 참조하지 못한다*
 ```

- 옵셔널 체이닝 연산자는 좌항 피연산자가 false로 평가되는 값이라도 null 또는 undefined가 아니면 우항의 프로퍼티 참조를 이어갈 수 있다.

```javascript
var str = "";

var length = str?.length;

console.log(length); *// 0  : 문자열의 길이를 참조했다*
```



### **<u>9.4.3 null 병합 연산자</u>**

- **<u>*null 병합 연산자*</u>**  : 좌항의 피연산자가 null 또는 undefined인 경우 우항의 피연산자를 반환하고, 그렇지 않으면 좌항의 피연산자를 반환한다

- 변수에 기본값을 설정할 때 유용하다

  `var foo = null ?? "default string";`

  `console.log(foo); *// 'default string'*`

- null 병합 연산자 도입 이전엔 논리연산자를 이용한 단축 평가를 통해 변수에 기본값을 설정했으나 false 값인 0 이나 

  ' ' 도 기본값으로서 유효하면 예기치 않는 동작이 발생할 수 있다

  `var foo = '' || 'default string';`

  `console.log(foo); *// foo가 false 이므로, 우항을 반환한다 : 'default string'*`

- null 병합 연산자는 좌항 피연산자가 false로 평가되는 값이라도 null 또는 undefined가 좌항의 피연산자를 반환한다

  `var foo = "" ?? "default string";`

  `console.log(foo); *// ""*`



------

# 10 객체 리터럴



## 10.1 객체란?

- 원시 값 (=변경 불가능한 값)을 제외한 나머지 값은 모두 객체다. (함수,배열,정규표현식 등)

- 원시 값은 변경 불가능한 값이지만 객체는 변경 가능한 값이다.

- 0개 이상의 프로퍼티로 구성된 집합이며 프로퍼티는 키 key와 값value로 구성된다

```javascript
var person ={

  name:'lee',   *//프로퍼티*

  age:20     *//프로퍼티*

}
```



------

## 10.2 객체 리터럴에 의한 객체 생성

- 가장 일반적인 객체 생성 방법 : 객체 리터럴 사용
- 코드 블록의 중괄호 뒤에는 세미콜론을 붙이지 않는다
- 단, 객체 리터럴의 닫는 중괄호 뒤에는 세미콜론을 붙인다



------

## 10.3 프로퍼티

***<u>프로퍼티</u>***  : 객체는 프로퍼티의 집합. 프로퍼티는 키와 값으로 구성된다

- 프로퍼티 키는 반드시 식별자 네이밍 규칙을 따라야 하는 것은 아니지만, 식별자 네이밍 규칙을 따르지 않는 이름에는 반드시 따옴표를 사용해야 한다

```javascript
  var person ={

  firstName : 'Ung-mo',  *//식별자 네이밍 규칙을 준수하는 프로퍼티 키 : 따옴표 생략 가능*

  'last-name' : 'Lee'   *//식별자 네이밍 규칙을 준수하지 않은 프로퍼티 키 : 따옴표 생략 불가*

};
```

- 문자열 또는 문자열로 평가할 수 있는 표현식도 프로퍼티 키로 생성할 수 있다.

  이 경우에는 대활호 [ ... ] 로 묶어야 한다

```javascript
 var obj = {};

var a = "hello";

obj[a] = "world"; *//ES5 : 프로퍼티 키 동적 생성*

console.log(obj); *//{hello : "world"}*
```

- 프로퍼티 키에 문자열이나 심벌 값 외의 값을 사용하면 암묵적 타입 변환을 통해 문자열이 된다

```javascript
var foo = {

 0: 1,

 1: 2,

 2: 3,

};

console.log(foo); *// {0: 1, 1: 2, 2: 3} : 따옴표는 붙지 않지만 내부적으로 문자열로 변환*
```

- 이미 존재하는 프로퍼티 키를 중복 선언하면 나중에 선언한 프로퍼티가 먼저 선언된 프로퍼티를 덮어쓴다



------

## 10.4 메서드

- 프로퍼티 값이 함수일 경우, 일반 함수와 구분하기 위해 메서드라 부른다

```javascript
   var counter={
  
      num:0,         //프로퍼티
  
      increase:function(){  
        this.num++;    //this는 counter 를 가리킨다
  
      }             //메서드
  
    }
  
```



------

## 10.5 프로퍼티 접근

- 프로퍼티에 접근하는 방법

  > ***<u>마침표 표기법</u>*** : 마침표 프로퍼티 접근 연산자 ( . ) 
  >
  > ***<u>대활호 표기법</u>*** : 대괄호 프로퍼티 접근 연산자 [ ... ]

- 프로퍼티 키가 식별자 네이밍 규칙을 준수하는 이름이면 두 방법 모두 사용할 수 있다

  `var person = {`

   `name: "Lee",`

  `};`

  `console.log(person.name); *//Lee*`

  `console.log(person["name"]); *//Lee*`

- 대괄표 표기법을 사용하는 경우, 접근 연산자에 지정하는 프로퍼키 키는 반드시 따옴표로 감싸야 한다. 그렇지 않으면 자바스크립트 엔진은 식별자로 해석하여 선언된 name을 찾는다.

  `var person = {`

   `name: "Lee",`

  `};`

  `console.log(person[name]); *//ReferrenceError : name is not defined*`

- 단, 프로퍼티 키가 숫자로 이뤄진 문자열인 경우 따옴표를 생략할 수 있다

- 객체에 존재하지 않는 프로퍼티에 접근하면 undefined를 반환한다

  `var person = {`

   `name: "Lee",`

  `};`

  `console.log(person.age); *//undefined*`

  

------

## 10.6 프로퍼티 값 갱신

- 이미 존재하는 프로퍼티에 값을 할당 하면 프로퍼티 값이 갱신된다

 ```javascript
var person = {
   name: "Lee",
};
  person.name = "Kim";
  
  console.log(person.name); //"Kim"
  
 ```





------

## 10.7 프로퍼티 동적 생성

- 존재하지 않는 프로퍼티에 값을 할당하면 프로퍼티가 동적으로 생성되어 추가 된 후 값이 할당 된다

 ```javascript
var person = {
   name: "Lee",
  };
person.age = 20;

console.log(person); *//{name: "Lee", age: 20}*
 ```

  

------

## 10.8 프로퍼티 삭제

- delete 연산자는 객체의 프로퍼티를 삭제한다

- 만약 존재하지 않는 프로퍼티를 삭제하면 아무런 에러 없이 무시 된다

```javascript
var person = {
  
 name: "Lee",
  
 age: 20,
  
};
  
delete person.age; *//age 프로퍼티 삭제*
  
  console.log(person); *//{name: "Lee"}*
```

  



------

## 10.9 ES6에서 추가된 객체 리터럴의 확장 기능



### <u>10.9.1 프로퍼티 축약 표현</u>

- 프로퍼티 값으로 변수를 사용하는 경우 변수이름과 프로퍼티 키가 동일한 이름일 때 프로퍼티 키를 생략할 수 있다

```javascript
let x = 1, y = 2;
  
const obj ={ x, y };
  
  console.log(obj); *//{x:1 , y:2}*
```

  



## 10.9.2 계산된 프로퍼티 이름

- <u>***계산된 프로퍼티 이름***</u> : 문자열 또는 문자열 타입 표현식을 사용해 프로퍼티 키를 동적으로 생성한다

- ES5에서 계산된 프로퍼티 이름으로 프로퍼티를 생성하려면 객체 리터럴 외부에서 대괄호를 표기법을 사용해야 한다

  ```javascript
  var prefix = "prop";
  var i = 0;
  var obj = {};
  
  obj[prefix + "-" + ++i] = i;
  obj[prefix + "-" + ++i] = i;
  obj[prefix + "-" + ++i] = i;
  
  console.log(obj); //{prop-1: 1, prop-2: 2, prop-3: 3}
  ```



- ES6에선 객체 리터럴 내부에서도 계산된 프로퍼티 이름으로 프로퍼티 키를 생상할 수 있다

  ```javascript
  var prefix = "prop";
  var i = 0;
  var obj = {
    [`${prefix}-${++i}`]: i,
    [`${prefix}-${++i}`]: i,
    [`${prefix}-${++i}`]: i,
  };
  console.log(obj); //{prop-1: 1, prop-2: 2, prop-3: 3}
  ```

  

------

## 10.9.3 메서드 축약 표현

- ES5에서 메서드를 정의하려면 프로퍼티 값으로 함수를 할당한다

  ```javascript
  var obj = {
    name: "Lee",
    sayHi: function () {
      console.log("Hi " + this.name);
    },
  };
  
  obj.sayHi(); //Hi! Lee
  ```

- ES6에서 메서드를 정의할 때 function 키워드를 생략한 축약 표현을 사용할 수 있다

  ```javascript
  const obj = {
      name : "lee",
      sayHi(){
          console.log("hi! " + this.name);
      }
  };
  
  obj.sayHi();     // Hi! lee
  ```

- 단, ES6 메서드 축약 표현으로 정의한 메서드는 프로퍼티에 할당한 함수와 다르게 동작한다.

  26.2절 "메서드" 참고


## 27.4 배열 생성

## 27.1 배열이란?

------



## 27.2 자바스크립트 배열은 배열이 아니다

- 배열은 객체지만 일반 객체와는 구별되는 특징이 있다

|      구분       |          객체          |     배열      |
| :-------------: | :--------------------: | :-----------: |
|      구조       | 프로퍼티와 프로퍼티 값 | 인덱스와 요소 |
|    값의 참조    |      프로퍼티 키       |    인덱스     |
|    값의 순서    |           X            |       O       |
| length 프로퍼티 |           X            |       O       |

- 값의 순서와 length프로퍼티를 갖고 있는 배열은 <u>***반복문을 통해 순차적으로 값에 접근하기 적합한 자료구조***</u>이다.
- ***<u>밀집배열</u>***  : 동일한 크기의 메모리 공간이 빈틈없이 연속적으로 나열된 자료구조
- 인덱스를 통해 단 한번의 연산으로 임의의 요소에 접근하여 효율적인 동작 가능
- 단, 정렬되지 않은 배열에서 특정한 요소를 찾는 경우 처음부터 특정 요소를 발견할 때까지 차례대로 검색해야 한다
- 요소를 삽입하거나 삭제하는 경우 배열의 요소를 연속적으로 유지하기 위해 요소를 이동 시켜야 한다
- ***희소배열*** : 동일하지 않는 크기의 메모리 공간과 연속적으로 이어져 있지 않는 자료구조
- 자바스크립트의 배열은 인덱스로 배열 요소에 접근하는 경우는 일반적인 배열보다 느리지만 특정 요소를 검색하거나 삽입/삭제하는 경우에는 일반적인 배열보다 빠르다



------

## 27.3 length 프로퍼티와 희소 배열

- 일반적인 배열의 length는 배열의 길이와 요소의 갯수가 일치한다
- 단, 희소배열은 실제 요소 개수보다 언제나 크다

------

## 27.4 배열 생성

### 27.4.3 Array.of 

- 전달된 인수를 요소로 갖는 배열을 생성
- 전달된 인수가 1개 이고, 숫자이더라도 인수를 요소로 갖는 배열을 생성한다

```javascript
Array.of(1)   // [1]
```

### 27.4.4 Array.from

- 유사배열객체 또는 이터러블 객체를 인수로 전달받아 배열로 변환하여 반환

```javascript
Array.from({length:2 , 0:'a', 1:'b'});    // 유사배열 -> ['a','b']
Array.from('Hello');  					// 이터러블 -> ['H','e','l','l','o']

```

------

## 27.5 배열 요소의 참조

------

## 27.6 배열 요소의 추가와 갱신

- 0 이상의 정수 (또는 정수 형태의 문자열) 외의 값을 인덱스처럼 사용하면 요소가 아닌 프로퍼티가 생성된다
- 추가된 프로퍼티는 length 프로퍼티 값에 영향을 주지 않는다

------

## 27.7 배열 요소의 삭제

- delete 연산자를 통해 배열의 요소를 삭제하면 배열은 희소 배열이 된다 (권고하지 않음)

- 즉, length 프로퍼티의 값이 바뀌지 않는다

- Array.prototype.splice 사용을 권고

  ------

## 27.8 배열 메서드

- ES5부터 도입된 배열 메서드는 대부분 원본 배열을 직접 변경하지 않고 새로운 배열을 생성하여 반환하는 경우가 많다
- 원본 배열을 직접 변경하게 되면 외부 상태를 직접 변경하는 부수 효과가 있을 수 있으므로 직접 변경하지 않는 메서드 사용을 권장

### 27.8.1 Array.isArray

- 전달된 인수가 배열이면 true , 배열이 아니면 false를 반환

```javascript
//true
Array.isArray([]);
Array.isArray([1,2]);
Array.isArray(new Array());

//false
Array.isArray();
Array.isArray({});
Array.isArray(null);
Array.isArray(undefined);
Array.isArray(1);
Array.isArray('Array');
Array.isArray(true);
Array.isArray(false);
Array.isArray({0:1, lenght:1})
```



### 27.8.2 Array.prototype.indexOf

- 원본 배열에서 인수로 전달된 요소를 검색하여 인덱스를 반환
- 인수로 전달한 요소와 중복되는 요소가 여러 개라면 첫 번째로 검색된 요소의 인덱스를 반환
- 인수로 전달한 요소가 존재하지 않으면 -1 을 반환

```javascript
const arr = [1,2,3];
arr.indexOf(2);   // 1
arr.indexOf(4);   // -1
arr.indexOf(2,2); // 2  : 두 번째 인수 : 검색을 시작할 인덱스, 생략하면 처음부터 검색한다
```

- 배열에 특정 요소가 존재하는지 확인할 때 유용

```javascript
const foods = ['apple','banana','orange'];

//foods 배열에 'orange'요소가 있는지 검색한다
//존재하지 않으면 'orange'요소를 추가한다
if(foods.indexOf('orange') === -1){
    foods.push('orange');
}

console.log(foods);     //["apple"."banana","orange"]

```



- ES7에 도입된 Array.protorype.includes 메서드를 사용하면 가독성이 더 좋다

```javascript
const foods = ['apple','banana','orange'];

//foods 배열에 'orange'요소가 있는지 검색한다
//존재하지 않으면 'orange'요소를 추가한다
if(!foods.includes('orange')){
    foods.push('orange');
}

console.log(foods);     //["apple"."banana","orange"]
```



### 27.8.3 Array.prototype.push

- 인수로 전달받은 모든 값을 원본 배열의 마지막 요소로 추가하고 변경된 length 프로퍼티 값을 번환
- 원본 배열을 직접 변경한다

```javascript
const arr = [1,2];

let result = arr.push(3,4);
console.log(result);   //4  : length 값 반환

console.log(arr);      //[1,2,3,4]
```

- 추가할 요소가 하나뿐이라면 push메서드 보단 length 프로퍼티를 사용하여 마지막 요소에 직접 추가하는 것이 성능면에서 더 빠르다

```javascript
const arr = [1,2];

arr[arr.length] = 3;
console.log(arr);      //[1,2,3,]
```

- 원본 배열을 직접 변경하는 부수 효과가 있기 때문에 ES6 스프레드 문법을 사용하는 편이 좋다 (35장 참고)

### 27.8.4 Array.protype.pop

- 원본 배열에서 마지막 요소를 제거하고 제거한 요소를 반환한다
- 빈 배열이면  undefined를 반환한다
- 원본 배열을 직접 변경한다
- pop 와 push 메서드를 사용하여 스택을 구현할 수 있다
- ***스택*** : 데이터를 마지막에 밀어 넣고 마지막에 밀어 넣은 데이터를 먼저 꺼내는 후입 선출 방식

### 27.8.5 Array.prototype.unshift

- 인수로 전달받은 모든 값을 원본 배열의 선두에 요소로 추가하고 변경된 length 프로퍼티 값을 반환
- 원본 배열을 직접 변경한다
- 원본 배열을 직접 변경하는 부수 효과가 있기 때문에 ES6 스프레드 문법을 사용하는 편이 좋다 (35장 참고)

### 27.8.6 Array.prototype.shift

- 원본 배열에서 첫 번째 요소를 제거하고 제거한 요소를 반환
- 빈 배열이면  undefined를 반환한다
- 원본 배열을 직접 변경한다
- shift 와 push 메서드를 사용하여 큐를 구현할 수 있다
- <u>**큐**</u> : 데이터를 마지막에 밀어 넣고, 처음 데이터(가장 먼저 밀어 넣은 데이터)를 먼저 꺼내는 선입 선출 방식

### 27.8.7 Array.prototype.concat

- 인수로 전달된 값들(배열 또는 원시값)을 원본 배열의 마지막 요소로 추가한 후 새로운 배열을 반환
- 인수로 전달한 값이 배열인 경우 배열을 해체하여 새로운 배열의 요소로 추가한다
- push와 unshift 메서드를 사용할 경우 원본 배열을 반드시 변수에 저장해두어야 하지만
- concat 메서드를 사용할 경우 반환 값을 반드시 변수에 할당받아야 한다
- 인수로 전달받은 값이 배열인 경우push와 unshift 메서드는 배열 원본 그대로 요소로 추가하지만, concat 메서드는 배열을 해체하여 마지막 요소로 추가한다

```javascript
const arr = [3,4];

arr.unshift([1,2]);
arr.push([5,6]);
console.log(arr);  // [[1,2],3,4,[5,6]];

let result = [1,2].concat([3,4]);
result = result.concat([5,6]);
console.log(result);  //[1,2,3,4,5,6];
```

- ES6 스프레드 문법으로 대체할 수 있다

### 27.8.8 Array.prototype.splice

- 원본 배열 중간에 요소를 추가하거나 중간에 있는 요소를 제거하는 경우 사용
- 3개의 매개변수가 있으며 원본 배열을 직접 변경한다
  - start : 요소를 제거하기 시작할 인덱스
    - -1 : 마지막 요소
    - -n : 마지막에서 n번째 요소
  - deleteCount : start부터 제거할 요소의 개수
    - 0 : 아무런 요소도 제거하지 않는다 (옵션)
  - items : 제거한 위치에 삽입할 요소들의 목록
    - 생략 : 원본 배열에서 요소들을 제거하기만 한다 (옵션)

```javascript
const arr = [1,2,3,4];

const result = arr.splice(1,2,20,30); //인덱스1부터 2개의 요소를 제거하고, 그 자리에 새로운 요소 20,30을 삽입
console.log(result);     //[2,3]
console.log(arr);		//[1,20,30,4];
```

- 특정 요소를 제거하려면 indexOf 메서드를 통해 특정 요소의 인덱스를 취득한 다음 splice 메서드를 사용한다

```javascript
const arr = [1,2,3,1,2];
function remove(array,item){
    const index = array.indexOf(item); //제거할 item요소의 인덱스 반환
    if(index !== -1) array.splice(index,1);  //제거할 item요소가 있으면 제거한다
    return array;
}
console.log(remove(arr,2)); //[1,3,1,2]
console.log(remove(arr,10)); //[1,3,1,2]
```

- filter 메서드를 사용하여 특정 요소가 중복된경우 모두 제거한다

```javascript
const arr = [1,2,3,1,2];
function removeAll(array,item){
    return array.filter(v => v !== item);
};
console.log(removeAll(arr,2));   //[1,3,1]
```

### 27.8.9 Array.prototype.slice

- 인수로 전달된 범위의 요소들을 복사하여 배열로 반환
- 원본 배열은 변경되지 않는다
- 두 개의 매개변수를 갖는다
  - start : 복사를 시작할 인덱스
    - 음수 : 배열의 끝에서 인덱스를 나타난다 
      - 예) splice(-2) : 배열의 마지막 두 개의 요소를 복사하여 배열로 반환
  - end : 복사를 종료할 인덱스
    - 인덱스에 해당하는 요소는 복사되지 않는다
    - 생략 시 기본값은 length프로퍼티 값

- 매개변수를 모두 생략하면 원본 배열의 복사본을 생성하여 반환
  - 생성된 복사본은 <u>***얕은 복사***</u>(11.2.1절 참고)로 생성된다
  - 참고)
    - 얕은 복사 : 한 단계까지만 복사
    - 깊은 복사: 객체에 중첩되어 있는 객체까지 복사

```javascript
const todos = [
  {id:1, content:'HTML'},
  {id:2, content:'CSS'},
  {id:3, content:'JavaScript'},
];

const _todos = todos.slice();
console.log(_todos === todos);  //false : 참조값이 다른 별개의 객체이다
console.log(_todos[0] === todos[0])  //true : 참조값이 같다. 얕은 복사
```

- arguments,HTMLCollection,NodeList 와 같은 유사 배열 객체를 배열로 변환할 수 있다

```javascript
function sum(){
	var arr = Array.prototype.slice.call(arguments);
    console.log(arr);  //[1,2,3]
    
    return arr.reduce(function (pre,cur){
        return pre+cur;
    },0)
}
cosole.log(sum(1,2,3));; //6
```

- Array.from 메서드를 사용하면 더 간단하게 유사 배열 객체를 배열로 변환할 수 있다 (27.4.4절 참고)

### 27.8.10 Array.prototype.join

- 원본 배열의 모든 요소를 문자열로 변환한 후 인수로 전달받은 문자열(구분자)로 연결한 문자열을 반환
- 구분자는 생략 가능. 기본 구분자는 콤마(,) 이다

```javascript
const arr = [1,2,3,4];
arr.join();   // '1,2,3,4';
arr.join('');  //'1234';
arr.join(':');  //'1:2:3:4';
```

### 27.8.11 Array.prototype.reverse

- 원본 배열의 순서를 반대로 뒤집는다
- 원본 배열이 변경된다
- 반환값은 변경된 배열이다

```javascript
const arr= [1,2,3];
const result = arr.reverse();
console.log(arr);  //[3,2,1]
console.log(result); //[3,2,1]
```

### 27.8.12 Array.prototype.fill

- 인수로 전달받은 값을 배열의 처음부터 끝까지 요소로 채운다
- 원본 배열이 변경된다

```javascript
const arr = [1,2,3];
arr.fill(0);
console.log(arr); // [0,0,0];
```

- 두 번째 인수로 요소 채우기를 시작할 인덱스를 정할 수 있다

```javascript
const arr = [1,2,3];
arr.fill(0,1);
console.log(arr);  //[1,0,0];
```

- 세 번째 인수로 요소 채우기를 멈출 인덱스를 정할 수 있다

```javascript
const arr = [1,2,3,4,5];
arr.fill(0,1,3); //전달 받은 값 0을 배열의 인덱스 1부터 3 이전(인덱스 3 미포함)까지 요소로 채운다
console.log(arr);  //[1,0,0,4,5]
```

- 배열을 생성하면서 특정 값으로 요소를 채울 수 있다

```javascript
const arr = new Array(3);
console.log(arr);  //[empty *3]
const result = arr.fill(1);
console.log(arr); //[1,1,1]
console.log(result); //[1,1,1]
```

- 모든 요소를 하나의 값만으로 채울 수밖에 없는 단점이 있다
  - Array.from 메서드를 사용하여 두 번째 인수로 전달한 콜백 함수를 통해 요소값을 만들면서 배열을 채울 수 있다
  - Array.from 메서드는 두 번째 인수로 전달한 콜백 함수에 첫 번째 인수에 의해 생성된 배열의 요소값과 인덱스를 순차적으로 전달하면서 호출하고 콜백함수의 반환값으로 구성된 배열을 반환한다

```javascript
//인수로 전달받은 정수만큼 요소를 생성하고 0부터 1씩 증가하면서 요소를 채운다
const sequences = (length = 0) => Array.from({length}, (_,i)=> i);
//const sequences = (lenght = 0) => Array.from(new Array(length), _,i => i);
console.log(sequences(3));   //[0,1,2]
```

### 27.8.13 Array.prototype.includes

- 배열 내에 특정 요소가 포함되어 있는지 확인하고 true / false를 반환한다
- 첫째 인수 :검색할 대상

```javascript
const arr = [1,2,3];
arr.includes(2);   //true
arr.includes(100); //false
```

- 두 번째 인수 : 검색을 시작할 인덱스
  - 생략 할 경우 : 기본값 0
  - 음수 : length 프로퍼티 값과 음수 인덱스를 합산하여 (length + index) 검색 시작 인덱스 설정

- indexOf메서드를 사용해서 특정 요소가 있는지 확인할 수 있다
  - 단, 반환값이 -1인지 확인 해야하고
  - 배열에 NaN 이 포함되어 있는지 확인할 수 없다

```javascript
[NaN].indexOf(NaN) !== -1   //false
[NaN].includes(NaN);   	//true
```

----

### 27.8.14 Array.prototype.flat

- 인수로 전달한 깊이만큼 재귀적으로 배열을 평탄화 한다

```javascript
[1,[2,3,4,5]].flat();   //[1,2,3,4,5]
```

- 중첩 배열을 평탄화할 깊이를 인수로 전달할 수 있다
  - 생략할 경우 : 기본값 1
  - Infinity 인 경우 : 중첩 배열 모두를 평탄화 한다

```javascript
[1,[2,[3,[4]]]].flat();  //[1,2,[3,[4]]];
[1,[2,[3,[4]]]].flat(1); //[1,2,[3,[4]]];

[1,[2,[3,[4]]]].flat(2); //[1,2,3,[4]];
[1,[2,[3,[4]]]].flat().flat();  //[1,2,3,[4]];     -> 2번 평탄화한 것과 동일

[1,[2,[3,[4]]]].flat(Infinity);  //[1,2,3,4]; -> 배열 모두를 평탄화
```



------



## 27.9 배열 고차 함수

- ***<u>고차함수</u>*** : 함수를 인수로 전달하거나 함수를 반환하는 함수



### 27.9.1 Array.prototype.sort

- 배열의 요소를 정렬
- 원변 배열을 직접 변경
- 정렬된 배열을 반환한다
- 기본적으로 오름차순으로 정렬한다
- 내림차순으로 정렬하려면 sort메서드를 사용 후 reverse 메서드를 사용한다

```javascript
const fruits = ['Banana','Orange','Apple'];
fruits.sort();
console.log(fruits);  //['Apple','Banana','Orange'];
fruits.reverse();
console.log(fruits); //['Orange','Banana','Apple'];
```

- 숫자 요소로 이루어진 배열을 정렬하면, 숫자가 아닌 유니코드 코드 포인트의 순서를 따른다

```javascript
const points = [40,100,1,5,2,25,10];
points.sort();
console.log(points);  //[1,10,100,2,25,40,5] : 의도한 대로 정렬되지 않는다
```

- 따라서 숫자 요소를 정렬할 때는 sort 메서드에 정렬 순서를 정의하는 비교 함수를 인수로 전달해야 한다
  - 비교 함수는 양수나 음수 또는 0을 반환해야 한다
  - 비교 함수의 반환값이 0보다 작으면 비교 함수의 첫 번째 인수를 우선하여 정렬하고
  - 0이면 정렬하지 않는다
  - 0보다 크면 두 번째 인수를 우선하여 정렬한다

```javascript
const points = [40,100,1,5,2,25,10];
//오름차순 정렬. 비교 함수의 반환값이 0보다 작으면 a를 우선하여 정렬한다
points.sort((a,b) => a-b);
console.log(points);  //[1,2,5,10,25,40,100]

//숫자 배열에서 최소/최대값 취득
console.log(points[0], points[points.length -1]);   //1, 100

//내림차순 정렬. 비교 함수의 반환값이 0보다 작으면 b를 우선하여 정렬한다
point.sort((a,b) => b-a);
console.log(points);  //[100,40,25,10,5,2,1];

//숫자 배열에서 최소/최대값 취득
console.log(points[points.length -1], points[0]);  //1 100
```

- ***<u>객체를 요소로 갖는 배열을 정렬하는 방법</u>***

```javascript
const todos = [
    {id:3, content:"HTML"},
    {id:1, content:"CSS"},
    {id:2, content:"JavaScript"},
];

//key 는 프로퍼티 키
//프로퍼키 값이 문자열일 때 - 산술 연산으로 비교하면 NaN이 나오므로 비교 연산을 사용한다
//비교 함수는 양수/음수/0을 반환하면 되므로 - 산술 연산 대신 비교 연산을 사용할 수 있다
function compare(key){
    return (a,b) => (a[key] > b[key] ? 1 : (a[key] < b[key] ? -1 : 0));
}

//id를 기준으로 오름차순 정렬
todos.sort(compare('id'));
console.log(todos);

/*
 {id:1, content:"CSS"},
 {id:2, content:"JavaScript"},
 {id:3, content:"HTML"}
*/
```



### 27.9.2 Array.prototype.forEach

- for문을 대체할 수 있는 고차 함수
- 자신의 내부에서 반복문을 실행 한다
- 즉, 내부에서 반복문을 통해 자신을 호출한 배열을 순회하면서 수행해야 할 처리를 콜백함수로 전달받아 반복 호출한다

```javascript
const numbers = [1,2,3];
const pows = [];

numbers.forEach(item => pows.push(item **2));
console.log(pows);  //[1,4,9];
```

- forEach메서드는   3개의 인수(호출한 요소값 , 인덱스 , this(forEach메서드를 호출한 배열 자체))를 전달받을 수 있다

```javascript
// 인자 3개 (요소값,인덱스,this)
// JSON.stirngify 메서드 : 객체를 JSON 포맷의 문자열로 변환 (43.2.2절 참고)
[1,2,3].forEach((item,index,arr) =>{
    console.log(item , index, JSON.stringify(arr));
});

/*
1 , 0 , [1,2,3]
2 , 1 , [1,2,3]
3 , 2 , [1,2,3]
*/
```

- 원본 배열을 변경하지 않는다
- 단, 콜백 함수를 통해 원본 배열을 변경할 수 있다

```javascript
const numbers = [1,2,3];

//콜백 함수의 세 번째 매개변수 arr은 원본배열 numbers를 가리킨다
//따라서 arr를 직접 변경하면 원본 배열 numbers가 변경된다
numbers.forEach((item,index,arr) => {arr[index] = item **2;});
console.log(numbers);     //[1,4,9]
```

- 반환값은 언제나 undefined 이다
- 두 번째 인수로 forEach 메서드의 콜백 함수 내부에서 this로 사용할 객체를 전달 할 수 있다

```javascript
class Numbers{
	numberArray = [];
	multiply(arr){
        arr.forEach(item => this.numberArray.push(item * item)); //화살표 함수 내부에서 this를 참조하면 상위 스코프의 this를 참조
    }
}

const numbers = new Numbers();
numbers.multiply([1,2,3]);
console.log(numbers.numberArray); //[1,4,9];
```

- for문과 달리 break,contunue 문을 사용할 수 없기 때문에 배열의 모든 요소를 순회해야 한다
- 희소 배열인 경우 존재하지 않는 요소는 순회 대상에서 제외된다
- for 문에 비해 성능이 좋진 않지만 가독성이 더 좋다
- 따라서 요소가 많은 배열을 순회하거나 시간이 많이 걸리는 복잡한 코드, 높은 성능이 필요한 경우가 아니라면 forEach 사용할 것을 권장

### 27.9.3 Array.prototype.map

- 자신을 호출한 배열의 모든 요소를 순회하면서 인수로 전달 받은 콜백함수를 반복 호출한다
- 콜백 함수의 반환값들로 구성된 새로운 배열을 반환
- 원본 배열은 변경되지 않는다

```javascript
const numbers = [1,4,9];
const roots = numbers.map(item => Math.sqrt(item));
console.log(roots);  //[1,2,3]
```

- forEach 와의 공통점
  - 자신을 호출한 배열의 모든 요소를 순회하면서 인수로 전달받은 콜백함수를 반복 호출
- **<u>*map 과 forEach 의 차이점*</u>**
  - forEach : 언제나 undefined를 반환  -> 단순히 반복문을 대체하기 위한 고차 함수
  - map : 새로운 배열을 반환 -> 요소값을 다른 값으로 매핑한 새로운 배열을 생성하기 위한 고차 함수
- map 메서드가 생성하여 반환하는 새로운 배열의 length 프로퍼티 값은 메서드를 호출한 배열의 lenght 프로퍼티 값와 반드시 일치한다
- 즉, 호출한 배열과 반환한 배열은 1:1 매핑한다
- 3개의 인수(호출한 요소값 , 인덱스 , this(map메서드를 호출한 배열 자체))를 전달받을 수 있다

```javascript
// 인자 3개 (요소값,인덱스,this)
// JSON.stirngify 메서드 : 객체를 JSON 포맷의 문자열로 변환 (43.2.2절 참고)
[1,2,3].map((item,index,arr) =>{
    console.log(item , index, JSON.stringify(arr));
    return item;
});

/*
1 , 0 , [1,2,3]
2 , 1 , [1,2,3]
3 , 2 , [1,2,3]
*/
```

- 두 번째 인수로 forEach 메서드의 콜백 함수 내부에서 this로 사용할 객체를 전달 할 수 있다

```javascript
class Prefixer{
    constructor(prefix){
        this.prefix = prefix;
    }
    
    add(arr){
        return arr.map(item => this.prefix + item);
    }
}

const prefixer = new Prefixer('-webkit-');
console.log(prefixer.add(['transition', 'user-select'])); //['-webkit-transition', '-webkit-user-select']
```

### 27.9.4 Array.prototype.filter

- 자신을 호출한 배열의 모든 요소를 순회하면서 인수로 전달받은 콜백함수를 반복 호출한다
- 콜백 함수의 반환값이 true인 요소로만 구성된 새로운 배열을 반환한다
- 원본 배열은 변경되지 않는다

```javascript
const numbers = [1,2,3,4,5];

//다음의 경우 numbers 배열에서 홀수인 요소만 필터링한다 (1은 true로 평가된다)
const odds = numbers.filter(item => item % 2);
console.log(odds);  //[1,3,5];
```

- forEach , map 메서드와 마찬가지로 자신을 호출한 배열의 모든 요소를 순회하면서 인수로 전달받은 콜백 함수를 반복 호출
- 차이점 :  반환값
  - forEach : undefined
  - map : 새로운 배열
  - filter : true인 요소만 추출한 새로운 배열
- 필터링 조건을 만족하는 특정 요소만 추출하여 새로운 배열을 만들 때 사용한다
- 따라서 반환한 새로운 배열의 lenght 프로퍼티 값은 메서드를 호출한 배열의 lenght 프로퍼티 값과 같거나 작을 수 있다
- 3개의 인수(호출한 요소값 , 인덱스 , this(filter메서드를 호출한 배열 자체))를 전달받을 수 있다
- 두 번째 인수로 forEach 메서드의 콜백 함수 내부에서 this로 사용할 객체를 전달 할 수 있다
- ***<u>자신을 호출한 배열에서 특정 요소를 제거하기 위해 사용할 수도 있다</u>***

```javascript
const users = [
    {id:1, name:'lee'},
    {id:2, name:'kim'},
];

const remove = (id) => {
    users.filter(user => user.id !== id);
};

users.remove(1);    //id가 1인 사용자를 제거
console.log(user);   //[{id:2, name:'kim'}]
```

- 특정 요소를 제거할 경우, 중복되어 있다면 중복된 요소가 모두 제거 된다
- ***<u>중복된 요소중에 하나만 제거하려면 indexOf 메서드를 통해 특정 요소의 인덱스를 취득한 다음 splice 메서드를 사용한다</u>***


### 27.9.5  Array.prototype.reduce

- 자신을 호출한 배열을 모든 요소를 순회하며 인수로 전달받은 콜백 함수를 반복 호출한다
- 콜백함수의 반환값을 다음 순회 시에 콜백함수의 첫 번째 인수로 전달하면서 콜백함수를 호출하여 하나의 결과값을 만들어 반환한다
- 원본 배열은 변경되지 않는다
- 첫번째 인수 : 콜백함수
  - 콜백함수 : 4개의 인수
    - 첫번째 : 초기값 또는 콜백함수의 이전 반환값
    - 두번째 : reduce 메서드를 호출한 배열의 요소값
    - 세번째 : 인덱스
    - 네번째 : reduce 메서드를 호출한 배열자체. this
- 두번째 인수 : 초기값

```javascript
//1부터 4까지 누적을 구한다
const sum = [1,2,3,4].reduce((accumulator, currentValue, index, array) => accumulator + currentValue, 0);
console.log(sum);   //10
```

- 콜백함수는 4개의 인수를 전달받아 배열의 lenght만큼 총4회 호출된다
- 이때 콜백함수로 전달되는 인수와 콜백함수의 반환값은 다음과 같다

|    구분     | accumulator (이전값) | currentValue | index |   array   |             반환값              |
| :---------: | :------------------: | :----------: | :---: | :-------: | :-----------------------------: |
| 첫번째 순회 |      0 (초기값)      |      1       |   0   | [1,2,3,4] | accumulator + currentValue = 1  |
| 두번째 순회 |          1           |      2       |   1   | [1,2,3,4] | accumulator + currentValue = 3  |
| 세번째 순회 |          3           |      3       |   2   | [1,2,3,4] | accumulator + currentValue = 6  |
| 네번째 순회 |          6           |      4       |   3   | [1,2,3,4] | accumulator + currentValue = 10 |

- 두 번째 인수로 전달하는 초기값은 옵션이다. 즉 생략 가능
- 하지만, 메서드를 호출할 땐 초기값을 전달하는 것이 안전하다
- recude 메서드는 하나의 결과값을 반환한다
- ***<u>자신을 호출한 배열의 모든 요소를 순회하며 하나의 결과값을 구해야 하는 경우에 사용한다</u>***
- 다양한 활용법
  - 평균 구하기
  - 최대값 구하기
  - 요소의 중복 횟수 구하기
  - 중첩 배열 평탄화
  - 중복 요소 제거

### 27.9.6 Array.prototype.some

- 자신을 호출한 배열의 요소를 순회하면서 인수로 전달된 콜백함수를 호출한다
- 콜백함수의 반환값이 단 한번이라도 참이면 true, 모두 거짓이면 false를 반환한다
- 즉, 정의한 조건을 만족하는 요소가 1개 이상 존재하는지 확인하여 그 결과는 불리언 타입으로 반환한다
- 단, 빈 배열인 경우 언제나 false를 반환한다
- 3개의 인수(호출한 요소값 , 인덱스 , this(some메서드를 호출한 배열 자체))를 전달받을 수 있다 (화살표 함수 사용 권장)

```javascript
[5,10,15].some(item => item > 10);  //true
[5,10.15].some(item => item < 0);   //false
['apple','banana','mango'].some(item => item === 'banana');  //true
[].some(item => item > 3);   //false
```



### 27.9.7 Array.prototype.every

- 자신을 호출한 배열의 요소를 순회하면서 인수로 전달된 콜백함수를 호출한다
- 콜백함수의 반환값이 모두 참이면 true, 단 한번이라도 거짓하면 false를 반환한다
- 즉, 배열의 모든 요소가 정의한 조건을 모두 만족하는지 확인하여 그 결과를 불리언 타입으로 반환한다
- 단, 빈 배열인 경우 언제나 true를 반환한다
- 3개의 인수(호출한 요소값 , 인덱스 , this(every메서드를 호출한 배열 자체))를 전달받을 수 있다 (화살표 함수 사용 권장)

### 27.9.8 Array.prototype.find

- 자신을 호출한 배열의 요소를 순회하면서 인수로 전달된 콜백함수를 호출하여 반환값이 true인 첫 번째 <u>***요소를 반환한다***</u>

- 콜백함수의 반환값이 true인 요소가 존재하지 않으면 undefined를 반환한다

- 3개의 인수(호출한 요소값 , 인덱스 , this(find 메서드를 호출한 배열 자체))를 전달받을 수 있다 (화살표 함수 사용 권장)

  ```javascript
  const users = [
      {id:1,name:'lee'},
       {id:2,name:'kim'},
       {id:2,name:'choi'},
       {id:3,name:'park'},
  ];
  users.find(user => user.id === 2);   // {id:2, name:'kim'}  -> 배열이 아닌 요소를 반환한다
  ```

  

### 27.9.9 Array.prototype.findIndex

- 자신을 호출한 배열의 요소를 순회하면서 인수로 전달된 콜백함수를 호출하여 반환값이 true인 첫 번째 요소의 ***<u>인덱스를 반환한다</u>***
- 콜백함수의 반환값이 true인 요소가 존재하지 않는다면 -1을 반환한다
- 3개의 인수(호출한 요소값 , 인덱스 , this(findIndex메서드를 호출한 배열 자체))를 전달받을 수 있다 (화살표 함수 사용 권장)

```javascript
const users = [
   {id:1,name:'lee'},
     {id:2,name:'kim'},
     {id:2,name:'choi'},
     {id:3,name:'park'}
];
users.findIndex(user => user.id === 2);  //1
users.findIndex(user => user.name === 'park');  //3

//위와 같이 프로퍼티 키와 프로퍼티 값으로 요소의 인덱스를 구하는 경우 다음과 같이 콜백함수를 추상화할 수 있다
function predicate(key,value){
    return item => item[key] === value;    //key와 value를 기억하는 클로저를 반환
}

users.findIndex(predicate('id',2)); //1   -> id기 2인 요소의 인덱스를 구한다
users.findIndex(predicate('name','park')); //3 -> name이 'park'인 요소의 인덱스를 구한다
```



### 27.9.10 Array.prototype.flatMap

- map 메서드를 통해 생성된 새로운 배열을 평탄화 한다
- 즉, map 메서드와 flat메서드를 순차적으로 실행하는 효과가 있다

```javascript
const arr = ['hello','world'];

//map과 flat을 순차적으로 실행
arr.map(x => x.split('').flat());  // ['h','e','l','l','o','w','o','r','l','d']
arr.flatMap(x => x.split(''));      // ['h','e','l','l','o','w','o','r','l','d']
```

- 단, flat메서드처럼 평탄화 깊이를 지정할 수는 없고 1단계만 평탄화 한다
- map메서드를 통해 생성된 중첩 배열의 평탄화 깊이를 지정해야 하면, flatMap 메서드를 사용하지 않고 map,flat 메서드를 각각 호출해야한다




------

# 34 이터러블

## 34.1 이터레이션 프로토콜

------

<u>***이터레이션 프로토콜***</u> : ES6에 도입되어 순회가능한 (= iterable 이터러블) 데이터 컬렉션(자료구조)을 만들기 위한 ECMAScript 사양에 정의하여 미리 약속한 규칙

- ES6 이전에는 순회 가능한 데이터 컬렉션 (배열,문자열,유사배열객체 등) 통일된 규약없이 for문,for ...in문 등으로 순회하였다
- ES6에선 데이터 컬렉션을 이터레이션 프로토콜을 준수하는 이터러블로 통일하여 for...of , 스프레드문법,배열 디스트럭처링 할당의 대상으로 사용할 수 있도록 통일화 했다
- 이터러블 프로토콜 
  - Sysmbol.iterator 메서드를 호출하면 이터레이터 프로토콜을 준수한 이터레이터를 반환한다
  - for ...문 , 스프레드문법, 배열 디스트럭처링 할당으로 사용 가능하다
- 이터레이터 프로토콜

### ***<u>34.1.1 이터러블</u>***

- 이터러블 프로토콜을 준수한 객체
- Sysmbol.iterator 메서드를 직접 구현하지 않거나 상속받지 않은 일반 객체는 이터러블 프로토콜을 준수한 이터러블이 아니다
- 따라서, 일반 객체는 for ..of문으로 순회할 수 없고, 스프레드 문법과 배열 디스트럭처링 할당의 대상으로 사용할 수 없다

```javascript
const obj = {a:1, b:2};
console.log(Symbol.iterator in obj); //false

for(const item of obj){   //TypeError
    console.log(item);
}
//배열 디스트럭처링 할당 대상으로 사용할 수 없다
const [a,b] = obj //TypeError

```

- 단, 현재 일반 객체에 스프레드 문법의 사용을 허용한다

```javascript
const obj = {a:1,b:2};
console.log({...obj}); //{a:1,b:2}
```

- 일반 객체도 이터러블 프로토콜을 준수하도록 구현하면 이터러블이 된다 (34.6절 참고)

### **<u>34.1.2 이터레이터</u>**

- 이터러블의 Symbol.iterator 메서드를 호출하면 이터레이터 프로토콜을 준수한 이터레이터를 반환한다
- next 메서드를 갖는다

```javascript
const array = [1,2,3]; //배열은 이터러블 프로토콜을 준수한 이터러블이다
const iterator = array[Symbol.iterator]();//Symbol.iterator 메서드는 이터레이터를 반환한다
console.log('next' in iterator); //true
```

- next 메서드는 이터러블의 각 요소를 순회하기 위한 포인터 역할을 한다
- next 메서드를 호출하면 이터러블을 순차적으로 한 단계씩 순회하며 결과를 나타내는 이터레이터 리절트 객체를 반환한다

```javascript
const array = [1,2,3];
const iterator = array[Symbol.iterator](); //Symbol.iterator메서드는 이터레이터를 반환한다.

//이터레이터 리절트 객체를 value와 done 프로퍼티를 갖는 객체이다
console.log(iterator.next()); //{value:1, done:false}
console.log(iterator.next()); //{value:2, done:false}
console.log(iterator.next()); //{value:3, done:false}
console.log(iterator.next()); //{value:undefined, done:true}
```

- value 프로퍼티 : 현재 순회 중인 이터러블의 값
- done 프로퍼티 : 이터러블의 순회 완료 여부

------

## 34.2 빌트인 이터러블

## 34.3 for ..of

- 이터러블을 순회하면서 이터러블의 요소를 변수에 할당한다
- for ...in문의 형식과 유사하다
- 내부적으로 이터레이터의 next 메서드를 호출하여 이터러블을 순회하며 next 메서드가 반환한 이터레이터 리절트 객체의 value 프로퍼티 값을 for ..of 문의 변수에 할당한다
- 이터레이터 리절트 객체의 done 프로퍼티 값이 false이면 순회를 계속하고 true이면 중단한다

```javascript
for(const item of [1,2,3]){
    console.log(item);   //1 2 3
}
```



------

## 34.4 이터러블과 유사 배열 객체

-  유사 배열 객체는 이터러블이 아닌 일반 객체이다
- 단, arguments, NodeList, HTMLCollection은 유사 배열 객체이면서 이터러블 이다

------































------

# 42 비동기 프로그래밍

## 42.1 동기 처리와 비동기 처리

- 자바스크립트 엔진은 한 번에 하나의 태스크(실행 대기 중)만 실행할 수 있는 싱글 스레드 방식으로 동작한다
- 그렇게 때문에 처리에 시간이 걸리는 태스크를 실행하는 경우 블로킹(작업중단)이 발생한다
- **<u>*동기(synchronous)*</u>** : 실행 중인 태스크가 종료할 때까지 다음에 실행될 태스크가 대기하는 방식
  - 태스크를 순서대로 하나씩 처리하므로 실행 순서가 보장된다
  - 앞선 태스크가 종료할 때까지 이후 태스크들은 블로킹 된다
- **<u>*비동기(asynchronous)*</u>** : 실행 중인 태스크가 종료되지 않는 상태여도 다음 태스크를 곧바로 실행하는 방식
  - 예) setTimeOut , setInterval, HTTP요청, 이벤트 핸들러
  - 블로킹이 발생하지 않지만 태스크의 실행 순서가 보장되지 않는다
  - 비동기 처리를 위한 콜백 패턴은 콜백 헬을 발생시켜 가독성을 나쁘게 한다

------

## 42.2 이벤트 루프와 태스크 큐

- ***<u>이벤트 루프</u>*** : 자바스크립트의 동시성을 지원하는 것
- 대부분의 자바스크립트 엔진은 크게 2개의 영역으로 구분한다
  - ***<u>콜 스택 (call stack)</u>*** : 소스코드(전역코드나 함수코드 등) 평가 과정에서 생성된 실행 컨텍스트가 추가되고 제거되는 스택 자료구조인 실행 컨텍스트
    - 함수를 호출하면 순차적으로 콜 스택에 푸시되어 순차적으로 실행된다
    - 자바스크립트 엔진은 단 하나의 콜 스택을 사용하기 때문에 최상위 실행 컨텍스트가 콜 스택에서 제거 되기 전까지는 다른 태스크를 실행하지 않는다
  - ***<u>힙 (heap)</u>*** :  객체가 저장되는 메모리 공간.
    - 콜 스택의 요소인 실행 컨텍스트는 힙에 저장된 객체를 참조한다
    - 메모리에 값을 저장하려면 먼저 값을 저장할 메모리 공단의 크기를 결정해야 하는데, 객체는 원시 값과는 다르게 크기가 정해져 있지 않으므로 할당해야 할 메모리 공간의 크기를 런타임에 결정해야 한다
    - 따라서 객체가 저장되는 메모리 공간인 힙은 구조화 되어 있지 않다는 특징이 있다
  - 콜 스택과 힙으로 구성되어 있는 자바스크립트 엔진은 태스크가 요청되면 콜 스택을 통해 요청된 작업을 순차적으로 실행할 뿐이다
  - **비동기 처리에서 소스코드의 평가와 실행을 제외한 모든 처리를 자바스크립트 엔진을 구동하는 브라우저 또는  Node.js가 담당한다**
    - 예를 들어 비동기 방식으로 동작하는 setTimeout의 콜백함수의 평가와 실행은 자바스크립트 엔진이 담당하지만 호출 스케줄링을 위한 타이머 설정과 콜백함수의 등록은 브라우저 또는 Node.js가 담당한다
  - 이를 위해 브라우저는 태스크 큐와 이벤트 루프를 제공한다
    - ***<u>태스크 큐</u>*** : 비동기 함수의 콜백 함수 또는 이벤트 핸들러가 일시적으로 보관되는 영역
      - 별도로 프로미스의 후속 처리 메서드의 콜백함수를 일시적으로 보관되는 마이크로태스크 큐도 존재한다 (45.7절 참조) 
    - ***<u>이벤트 루프</u>*** : 콜 스택에 실행 중인 실행 컨텍스트가 있는지, 그리고 태스크 큐에 대기 중인 함수가 있는지 반복해서 확인한다
      - 만약 콜스택이 비어 있고 태스크 큐에 대기 중인 함수가 있다면 순차적으로 태스크 큐에 대기 중인 함수를 콜 스택으로 이동 시킨다
      - 이때 콜 스택으로 이동한 함수는 실행된다.
      - 즉, 태스크 큐에 일시 보관된 함수들은 비동기 처리 방식으로 동작한다



------

# 43 Ajax

## 43.1 Ajax란?

- 자바스크립트를 사용하여 브라우저가 서버에게 비동기 방식으로 데이터를 요청하고 서버가 응답한 데이터를 수신하여 웹피이지를 동적으로 갱신하는 프로그래밍 방식
- 브라우저에서 제공하는 Web API인 XMLHttpRequest 객체를 기반으로 동작한다
  - XMLHttpRequest  : HTTP 비동기 통신을 위한 메서드와 프로퍼티 제공
- 서버로부터 웹페이지의 변경에 필요한 데이터만 비동기 방식으로 전송받아 웹피이지를 변경할 필요가 없는 부분은 다시 렌더링하지 않고 부분적으로 렌더링하는 방식

------

## 43.2 JSON

- 클라이언트와 서버 간의 HTTP 통신을 위한 텍스트 데이터 포맷
- 자바스크립트에 종속되지 않는 언어 독립형 데이터 포맷. 대부분 프로그래밍 언어에서 사용 가능

### <u>**43.2.1 JSON 표기 방식**</u>

- 키는 반드시 큰따옴표로 묶어야 한다
- 값은 객체 리터럴과 같은 표기법을 그대로 사용할 수 있다
- 문자열은 반드시 큰따옴표로 묶어야 한다



### <u>43.2.2 JSON.stringify</u>

- 객체를 JSON 포맷의 문자열로 변환한다
- ***<u>직렬화</u>*** : 클라이언트가 서버로 객체를 전송하기 위해 객체를 문자열화 하는 것
- 배열도 JSON 포맷의 문자열로 변환한다



### <u>43.2.3 JSON.parse</u>

- JSON 포맷의 문자열을 객체로 변환
- ***<u>역직렬화</u>*** : 문자열을 객체로서 사용하기 위해 JSON 포맷의 문자열을 객체화 하는 것



### <u>43.3 XMLHttpRequest</u>

- 브라우저는 주소창이나 HTML form / a 태그를 통해 HTTP 요청 전송 기능을 기본 제공한다
- 자바스크립트를 이용하여 HTTP 요청을 전송하려면 XMLHttpRequest 객체를 사용한다

### <u>43.3.1 XMLHttpRequest 객체 생성</u>

```javascript
const xhr = new XMLHttpRequest();
```



### <u>43.3.2 XMLHttpRequest 객체의 프로퍼티와 메서드</u>

- XMLHttpRequest 객체는 다양한 프로퍼티와 메서드를 제공한다
- XMLHttpRequest 객체의 프로토타입 프로퍼티

| 프로토타입 프로퍼티 | 설명                                                         |
| :------------------ | :----------------------------------------------------------- |
| readyState          | HTTP 요청의 현재 상태를 나타내는 정수. 다음과 같은 XMLHttpRequest 정적 프로퍼티를 값으로 갖는다                                                 UNSENT : 0 , OPENED : 1 , HEADERS_RECEIVED : 2 , LOADING : 3, DONE : 4 |
| status              | HTTP 요청에 대한 응답 상태 (HTTP 상태 코드)를 나타내는 정수 예)200 |
| statusText          | HTTP 요청에 대한 응답 메세지를 나타내는 문자열  예)"OK"      |
| responseType        | HTTP 응답 타입  예)document, json, text, blob, arraybuffer   |
| response            | HTTP 요청에 대한 응답 몸체(response body), responseType에 따라 타입이 다르다 |
| responseText        | 서버가 전송한 HTTP 요청에 대한 응답 문자열                   |

- XMLHttpRequest 객체의 이벤트 핸들러 프로퍼티
- XMLHttpRequest  객체의 메서드
- XMLHttpRequest 객체의 정적 프로퍼티

### <u>43.3.3 HTTP 요청전송</u>

- HTTP 요청을 전송하는 경우 다음 순서를 따른다
  - XMLHttpRequest.prototype.open 메서드로 HTTP 요청을 초기화 한다
  - 필요에 따라 XMLHttpRequest.prototype.setRequestHeader 메서드로 특정 HTTP 요청 헤더 값을 설정한다
  - XMLHttpRequest.prototype.send 메서드로 HTTP 요청을 전송한다
- XMLHttpRequest.prototype.open
  - 서버에 전송할 HTTP 요청을 초기화 한다
- XMLHttpRequest.prototype.send
  - open 메서드로 초기화된 HTTP 요청을 서버에 전송한다
  - 기본적으로 서버로 전송하는 데이터는 GET,POST 요청 메서드에 따라 전송 방식에 차이가 있다
    - GET : 데이터를 URL의 일부분인 쿼리 문자열로 서버에 전송
    - POST : 데이터(페이로드)를 요청 몸체 (request body)에 담아 전송
  - 페이로드가 객체인 경우 반드시 JSON.stringify 메서드를 사용하여 직렬화한 다음 전달해야 한다
- XMLHttpRequest.prototype.setRequestHeader
  - 특정 HTTP 요청의 헤더 값을 설정한다
  - 반드시 open 메서드를 호출한 이후에 호출해야 한다
  - Content-type : HTTP 요청 헤더 중 하나. 요청 몸체에 담아 전송할 데이터의 MIME 타입의 정보를 표현한다
  - HTTP 클라이언트가 서버에 요청할 때 서버가 응답할 데이터의 MIME 타입을 Accept로 지정할 수 있다
  - 만약 Accept 헤더를 설정하지 않으면 send 메서드가 호출될 때 Accept 헤더가 */* 으로 전송된다

```javascript
xhr.setRequestHeader('accept', 'application/json');
```



### <u>43.3.4 HTTP 응답처리</u>

- 서버가 전송한 응답을 처리하려면 XMLHttpRequest 객체가 발생시키는 이벤트를 캐치해야 한다
- XMLHttpRequest 객체는 다양한 이벤트 핸들러 프로퍼티를 갖는데, 그 중에서 HTTP 요청의 현재 상태를 나타내는 readyState 프로퍼티 값이 변경된 경우 발생하는 readystatechange 이벤트를 캐치하여 다음과 같이 HTTP 응답을 처리할 수 있다.

------

# 44 REST API



- REST : HTTP를 기반으로 클라이언트가 서버 리소스에 접근하는 방식을 규정한 이케텍처
- REST API : REST를 기반으로 서비스 API를 구현한 것

## 44.1 REST API의 구성



| 구성 요소 |              내용              |    표현 방법     |
| :-------: | :----------------------------: | :--------------: |
|   자원    |              자원              | URI (엔드포인트) |
|   행위    |        자원에 대한 행위        | HTTP 요청 메서드 |
|   표현    | 자원에 대한 행위의 구체적 내용 |     페이로드     |



------



## 44.2 REST API 설계 원칙

- URI는 리소스를 표현해야 한다
- 리소스를 식별할 수 있는 이름은 동사보다는 명사를 사용한다.
- 리소스에 대한 행위는 HTTP 요청 메서드로 표현한다



| HTTP 요청 메서드 |       종류       |         목적          | 페이로드 |
| :--------------: | :--------------: | :-------------------: | :------: |
|       GET        | index / retrieve | 모든/특정 리로스 취득 |    X     |
|       POST       |      create      |      리소스 생성      |    O     |
|       PUT        |     replace      |  리소스의 전체 교체   |    O     |
|      PATCH       |      modify      |  리소스의 일부 수정   |    O     |
|      DELETE      |      delete      | 모든/특정 리소스 삭제 |    X     |



------

# 45 Promise

- 자바스크립트는 비동기 처리를 위한 하나의 패턴으로 콜백 함수를 사용한다
- 콜백 패턴은 콜백 헬로 인해 가독성이 나쁘고, 비동기 처리 중 발생한 에러의 처리가 곤란하며 여러 개의 비동기 처리를 한번에 처리하는 데도 한계가 있다
- ES6에서 비동기 처리를 위한 프로미르를 도입하여 콜백 패턴이 가진 단점을 보완하였다



## 45.1 비동기 처리를 위한 콜백 패턴의 단점

------

### 45.1.1 콜백 헬

- setTimeout 함수는 비동기 함수인 이유는 콜백 함수의 호출이 비동기로 동작하기 때문이다
- setTimeout 함수를 호출하면 콜백함수를 호출 스케줄링한 다음, **타이머 id를 반환하고 즉시 종료된다.**
- 즉, setTimeout의 콜백함수는 setTimeout 함수가 종료된 이후에 호출된다.
- 따라서 setTimeout 함수 내부의 콜백함수에서 처리 결과를 기대한 대로 반환하거나 할당할 수 없다

```javascript
let g = 0 ;
//비동기 함수인 setTimeout 함수는 콜백함수의 처리 결과를 외부로 반환하거나 상위 스포크의 변수에 할당하지 못한다
setTimeout(()=> {g = 100;}, 0);
console.log(g);     // 0
```

- GET 요청을 전송하고 서버의 응답을 받는 get함수도 비동기 함수이다.

```javascript
//GET 요청을 위한 비동기 함수
const get = url =>{
    const xhr = new XMLHttpRequest();
    xhr.open('GET', url);//요청 초기화
    xhr.send();          //요청 전송
    
    xhr.onload = () =>{
        if(xhr.status === 200){
            // 1. 서버의 응답 반환
            return JSON.parse(xhr.response);
        }
        console.error('${xhr.status ${xhr.statusText}');
    };
};

// 2. id가 1인 post 취득
const response = get('https://jsonplacehoder.tplicode.,com/post/1');
console.log(response);   //undefined
```

- get 함수가 호출되면 XMLHttpRequest 객체를 생성
- HTTP 요청 초기화 -> HTTP 요청 전송
- xhr.onload 이벤트 핸들러 프로퍼티에 이벤트 핸들러를 바인딩하고 종료한다
- 이때 get 함수에 명시적인 반환문이 없으므로 undefined를 반환한다.
- xhr.onload 이벤트 핸들러 프로퍼티에 바인딩한 이벤트 핸들러의 반환문(1.)은 get함수의 반환문이 아니다
- get 함수가 종료되면 get함수의 실행 컨텍스트가 콜스택에서 팝되고
- 곧바로 (2.)의 console.log가 실행된다. 
- 이때 console.log의 실행 컨텍스트가 생성되어 실행 컨텍스트 스택에 푸시된다
- 서버로부터 응답이 도착하면 load이벤트가 발생한다
- **이때  xhr.onload 핸들러 프로퍼티에 바인딩한 이벤트 핸들러가 즉시 실행되는 것이 아니라 load이벤트가 발생 발생하면 태스크 큐에 저장되어 대기하다가 콜 스택이 비어 있게 되면 이벤트 루프에 의해 콜스택으로 푸시되어 실행된다.**
- 비동기 함수의 처리결과(서버의 응답 등)에 대한 후속 처리를 비동기 함수 내부에서 수행해야 한다
- 이때, 일반적으로 콜백함수를 사용하게 된다

```javascript
//GET 요청을 위한 비동기 함수
const get = (url,seccessCallback,failureCallback) =>{
    const xhr = new XMLHttpRequest();
    xhr.open('GET', url);//요청 초기화
    xhr.send();          //요청 전송
    
    xhr.onload = () =>{
        if(xhr.status === 200){
            // 1. 서버의 응답을 콜백함수에 인수로 전달하면서 호출하여 응답에 대한 후속 처리를 함
            successCallback(JSON.parse(xhr.response));
        }
            //에러 정보를 콜백함수 인수로 전달하면서 호출하여 에러 처리를 함
        	failureCallback(xhr.status);
    };
};

// 2. id가 1인 post 취득
//서버의 응답에 대한 후속처리를 위한 콜백함수를 비동기 함수인 get에 전달해야 한다
const response = get('https://jsonplacehoder.tplicode.,com/post/1', console.log, console.error);
/*
{
	"userId":1,
	 ...
}
*/
```

- 콜백함수를 통해 비동기 처리 결과에 대한 후속처리를 수행하는 비동기 함수가 결과를 가지고 또 다시 비동기 함수를 호출해야 하는 복잡도 발생

### <u>45.1.2 에러 처리의 한계</u>

- 콜백 패턴의 문제점 중 하나는 에러처리가 힘들다는 것

```javascript
//1초 후에 콜백함수가 실행되도록 타이머를 설정하고, 이후 콜백함수는 에러를 발생시킨다
try{
    setTimeout(()=> {throw new Error('Error!');}, 1000);
}catch (e){
    console.log("캐치한 에러",e);
}
```

- 위 코드에서 발생한 에러는 catch 코드 블록에서 캐치 되지 않는다
  - setTimeout 함수의 콜백함수가 실행될 때 setTimeout 함수는 이미 콜스택에서 제거된 상태
  - 즉, 콜백함수를 호출한 것이 setTimeout  함수가 아니라는 것을 의미한다
- 에러는 호출자 방향으로 전파된다
- 즉, 콜스택의 아래 방향 (실행 중인 실행 컨텍스트가 푸시되기 직전에 푸시된 실행 컨텍스트 방향)으로 전파된다.
  - 위 코드에서 콜백함수를 호출한 것은 setTimeout 이 아니기 때문에 catch에서 캐치 되지 않는다

------

## 45.2 프로미스의 생성

- ES6에 도입되어, 호스트 객체가 아닌 ECMAScript 사양에 정의된 표준 빌트인 객체이다
- 비동기 처리를 수행할 콜백함수를 인수로 전달받고, 해당 콜백함수를 resolve(비동기처리 성공)와 reject(실패)함수를 인수로 전달 받는다

```javascript
const promiseGet = url => {
    const xhr = new XMLHttpRequest();
	xhr.open('GET',url);
	xhr.send();

	xhr.onload=()=>{
        if(xhr.statues === 200){
            resolve(JSON.parse(xhr.response));
        }else{
            reject(new Error(xhr.status));
        }
    };
};
promiseGet('https://jsonplacehoder.tplicode.com/post/1');
```

- 프로미스의 진행 상태

| 상태 정보 |                 의미                  |          상태 변경 조건          | 처리 결과 |
| :-------: | :-----------------------------------: | :------------------------------: | :-------: |
|  pending  | 비동기 처리가 아직 수행되지 않은 상태 | 프로미스가 생성된 직후 기본 상태 |           |
| fulfilled |   비동기 처리가 수행된 상태 (성공)    |        resolve 함수 호출         |   value   |
| rejected  |   비동기 처리가 수행된 상태 (실패)    |         reject 함수 호출         |   error   |

- 비동기 처리 성공 : resolve 함수를 호출해 프로미스를 fulfilled 상태로 변경
- 비동기 처리 실패 : reject 함수를 호출해 프로미스를 rejected 상태로 변경
- **settled** 상태 : fulfilled 또는 rejected 상태 , 상태와 상관 없이 pending이 아닌 상태. 즉, 비동기 처리가 수행된 상태
  - settled 상태가 되면 다른 상태로 변화할 수 없다
- 비동기 처리가 성공하면 프로미스는 **결과인 1**을 값으로 갖는다
- 실패시 **Error 객체**를 값으로 갖는다

------

## 45.3 프로미스의 후속 처리 메서드

- 비동기 처리 상태 변화 후 이에 따른 후속 처리를 위해 then,catch,finally 메서드를 제공한다
- 비동기 처리 상태가 변화하면 후속 처리 메서드에 인수로 전달한 콜백함수가 선택적으로 호출된다
- 모든 후속 처리 메서드는 프로미스를 반환하고, 비동기로 동작한다

### <u>45.3.1 Promise.prototype.then</u>

- 두 개의 콜백함수를 인수로 전달 받는다
  - 첫번째 콜백함수 : 프로미스가 fulfilled가 되면 호출된다. 프로미스의 비동기 처리 결과를 인수로 전달받는다
  - 두번째 콜백함수 : 프로미스가 rejected가 되면 호출된다. 프로미스의 에러를 인수로 전달받는다

```javascript
//fulfilled
new Promise(resolve => resolve('fulfilled')).then(v => console..log(v), e => console.error(e));   //fulfilled

//rejected
new Promise(( _, resolve) => reject(new Error('rejected'))).then(v => console.log(v), e => console.log(error(e)); //Error:rejected
```

-  then은 언제나 프로미스를 반환한다
-  만약 콜백함수가 프로미스가 아닌 값을 반환하면 그 값을 암묵적으로 resolve 또는 reject 하여 프로미스를 생성해 반환한다



### <u>45.3.2 Promise.prototype.catch</u>

- 한 개의 콜백함수를 인수로 전달받는다
- 콜백함수는 프로미스가 rejected 상태인 경우만 호출된다

```javascript
//rejected
new Promise((_, reject) => reject(new Error('rejected'))).catch(e => console.log(e)); //Error:rejected
```

- then(undefined,onRejected)와 동일하게 동작한다
- 언제나 프로미스를 반환한다



### <u>45.3.3 Promise.prototype.finally</u>

- 한 개의 콜백함수를 인수로 전달받는다
- 프로미스의 성공,실패 상관없이 무조건 한 번 호출된다
- 프로미스의 상태와 상관없이 공통적으로 수행해야 할 처리 내용이 있을 때 유용하다
- 언제나 프로미스를 반환한다

```javascript
new Promise(()=>{}).finally(()=> console.log('finally'));   //finally
```

------

## 45.4 프로미스의 에러 처리

- then 메서드에 두 번째 콜백 함수를 전달하는 것 보다 catch메서드를 사용하는 것이 더 가독성이 좋고 명확하다
- 따라서 에러 처리는 catch 메서드에서 하는 것을 권장

------

## 45.5 프로미스 체이닝

- **<u>*프로미스 체이닝*</u>** : then, catch finally 후속 처리 메서드는 언제나 프로미스를 반환하므로 연속적으로 호출 할 수 있다

------

## 45.6 프로미스의 정적 메서드

### <u>45.6.1 Promise.resolve / Promise.reject</u>

- 이미 존재하는 값을 래핑하여 프로미스를 생성하기 위해 사용

### <u>45.6.2 Promise.all</u>

- 여러 개의 비동기 처리를 모두 병렬 처리할 때 사용

```javascript
const requestData1 = () =>
    new Promise(resolve => setTimeout(() => resolve(1), 3000));
const requestData2 = () =>
    new Promise(resolve => setTimeout(() => resolve(2), 2000));
const requestData3 = () =>
    new Promise(resolve => setTimeout(() => resolve(3), 1000));

//세 개의 비동기 처리를 순차적으로 처리
const res = [];
requestData1().then(data => {
    res.push(data);
    return requestData2();
})
.then(data => {
    res.push(data);
    return requestData3();
})
.then(data => {
    res.push(data);
    console.log(res); //[1,2,3]  => 약 6초 소요
})
.catch(console.error);
```

- 위 예제는 세 개의 비동기 처리는 서로 의존하지 않고 개별적으로 수행된다
- 따라서 비동기 처리를 순차적으로 처리할 필요가 없다

```javascript
const requestData1 = () =>
    new Promise(resolve => setTimeout(() => resolve(1), 3000));
const requestData2 = () =>
    new Promise(resolve => setTimeout(() => resolve(2), 2000));
const requestData3 = () =>
    new Promise(resolve => setTimeout(() => resolve(3), 1000));

//세 개의 비동기 처리를 병렬로 처리
Promise.all([requestData1(), requestData2(), requestData3()]).then(console.log) //[1,2,3]  약 3초소요
.catch(console.error);
```

- 프로미스를 요소로 갖는 배열 등의 이터러블을 인수로 전달 받는다
- 전달 받은 모든 프로미스가 fulfilled 상태가 되면 모든 처리 결과를 배열에 저장해 새로운 프로미스를 반환한다
- 인수로 전달받은 프로미스가 하나라도 rejected 상태가 되면 나머지 프로미스가 fufilled 상태가 되는 것을 기디리지 않고 즉시 종료한다
- 인수로 전달받은 이터러블 요소가 프로미스가 아닌 경우 Promise.resolve 메서드를 통해 프로미스로 래핑한다

### <u>45.6.3 Promise.race</u>

- 프로미스를 요소로 갖는 배열 등의 이터러블을 인수로 전달 받는다
- 가장 먼저 fulfilled 상태가 된 프로미스의 처리 결과를 resolve하는 새로운 프로미스를 반환한다
- 인수로 전달받은 프로미스가 하나라도 rejected 상태가 되면 나머지 프로미스가 fufilled 상태가 되는 것을 기디리지 않고 즉시 종료한다



### 45.6.4 Promise.allSettled

- 프로미스를 요소로 갖는 배열 등의 이터러블을 인수로 전달 받는다
- 전달 받은 프로미스가 모두 settled상태 (비동기 처리가 수행된 상태)가 되면 처리 별과를 배열로 반환한다
- 처리 결과를 나타내는 객체
  - fulfilled 상태 : 비동기 처리 상태를 나타내는 status 프로퍼티와 처리 결과를 나타내는 value 프로퍼티
  - rejected 상태 : 비동기 처리 상태를 나타내는 status 프로퍼티와 에러를 나타내는 reason 프로퍼티

------

## 45.7 마이크로태스크 큐

```javascript
//로그가 출력 되는 순서는..?

setTimeout(()=> console.log(1), 0);
Promise.resolve()
	.then(()=>console.log(2));
	.then(()=>console.log(3));

// 2->3->1
```

- 프로미스의 후속 처리 메서드의 콜백함수는 태스크 큐가 아니라 마이크로태스크 큐에 저장 된다
- ***<u>마이크로태스크 큐</u>*** :  태스크 큐와는 별도의 큐. 프로미스의 후속처리 메서드의 콜백함수가 일지 저장된다
  - 태스크 큐보다 우선순위가 높다

------

## 45.8 fetch

- XMLHttpRequest 객체와 마찬가지로 HTTP 요청 전송 기능을 제공하는 클라이언트 사이드 Web API
- XMLHttpRequest  객체보다 사용법이 간단하고 프로미스를 지원한다 **(IE 미지원)**
- HTTP 요청을 전송한 URL , HTTP 요청 메서드, HTTP 요청 헤더, 페이로드 등을 설정한 객체를 전달한다
- HTTP 응답을 나타내는 Response 객체를 래핑한 Promise 객체를 반환한다
- 

# 46 제너레이터

## 46.1 제너레이터란?

------

- ES6에 도입되어 코드 블록의 실행을 일시 중지했다가 필요한 시점에 재개할 수 있는 함수
- 함수 호출자에게 함수 실행의 제어권을 양도할 수 있다
  - 일반 함수를 호출하면 제어권이 함수에게 넘어가고, 호출자는 이후 함수 실행을 제어할 수 없다
- 함수 호출자와 함수의 상태를 주고 받을 수 있다
  - 일반 함수가 실행되고 있는 동안에서 함수 외부에서 내부로 값을 전달하여 함수의 상태를 변경할 수 없다
  - 제너레이터는 함수 호출자에게 상태를 전달할 수 있고 호출자로부터 상태를 전달받을 수 있다
- 호출하면 제너레이터 객체를 반환한다
  - 함수 코드를 실행하는 것이 아니라 이터러블이면서 동사에 이터레이터인 제너레이터 객체를 반환한다

------



## 46.2 

- function* 키워드로 선언, 하나 이상의 yield 표현식을 포함한다

```javascript
//선언문
function* genDecFunc(){
    yield 1;
}

//표현식
const genExpFunc = function*(){
    yield 1;
};

//메서드
const obj = {
    * genObjMethod(){
        yield 1;
    }
};

//클래스 메서드
class MyClass{
    * genClsMethod(){
        yield 1
    }
}

```

- 에스터리스크(*) 의 위치는 function키워드와 함수 이름 사이라면 어디든 상관으나 function키워드 바로 뒤에 붙이는 것을 권장한다
- 제너레이터 함수는 화살표 함수로 정의할 수 없다

```javascript
const genArrowFunc = * () =>{
    yield 1;
};  //SyntaxError : unexpected toked '*'
```

- new 연산자와 함께 생성자 함수로 호출할 수 없다

```javascript
function* genFunc(){
	yield 1;
}
new genFunc(); //TypeError: genFunc is not a constructor
```

------

## 46.6 제너레이터의 활용

### *<u>**46.6 async/await**</u>*

- 제너레이터를 사용해서 비동기 처리를 동기 처럼 구현할 수 있게 되었지만 코드가 장황해지고 가독성이 나빠졌다
- ES8에서 제너레이터보다 간단하고 가독성 좋게 비동기 처리를 동기 처럼 동작하도록 구현할 수 있는 async/await이 도입
- 프로미스를 기반으로 동작하기 때문에 then/catch/finally 후속 처리 메서드를 할 필요없이 마치 동기 처럼 프로미스를 사용할 수 있다

**<u>*46.6.1 async 함수*</u>**

- await 키워드를 반드시 async 함수 내부에서 사용해야 한다
- async 함수는 키워드를 사용해 정의하며 언제나 프로미스를 반환한다

***<u>46.6.2 await 키워드</u>***

- await 키워드를 프로미스가 settled 상태 (비동기 처리가 수행된 상태)가 될 때까지 대기하다가 settled 상태가 되면 프로미스가 resolve한 처리 결과를 반환한다 .

```javascript
const fetch = require('node-fetch');
const getGithubUserName = async id = {
    const res = await fetch('https://api..../${id}'); //1
	const {name} = await res.json(); 				//2
	console.log(name)  					// BR Lee
};
getGithubUserName('Name2');
```

- 1 의 fetch 함수가 수행한 HTTP 요청에 대한 서버의 응답이 도착해서 fetch 함수가 반환한 프로미스가 settled 상태가 될 때까지 1.은 대기하게 된다
- 이후 프로미스가 settled 상태가 되면 프로미스가 resolve한 처리 결과가 res 변수에 할당된다

***<u>46.6.3 에러 처리</u>***

- 비동기 처리를 위한 콜백 패턴의 단점 중 하나는 에러 처리가 곤란하다는 것
- async/await 에서는 try ... cath문을 사용할 수 있다

```javascript
const fetch = require('node-fetch');
const foo = async () =>{
    try{
        const wrongUrl = 'https://worng.url';
        const response = await fetch(wrongUrl);
        const data = await response.json();
        console.log(data);
    }catch(err){
        console.error(err);
    }
}
foo();
```

- catch 문을 사용해서 에러 처리를 하지 않으면 async 함수는 발생한 에러를 reject 하는 프로미스를 반환 하기 때문에 asyng 함수를 호출하고 Promise.prototype.cath 후속 처리 메서드를 사용하여 에러를 캐치할 수 있다

```javascript
const fetch = require('node-fetch');
const foo = async () =>{
        const wrongUrl = 'https://worng.url';
        const response = await fetch(wrongUrl);
        const data = await response.json();
        return data;

}
foo()
	.then(console.log)
	.catch(console.error);
```

