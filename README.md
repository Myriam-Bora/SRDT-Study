## *목차*
<br>

### [04 변수](#04-변수)

**[4.1 변수란 무엇인가? 왜 필요한가?](#41-변수란-무엇인가-왜-필요한가)**

**[4.2 식별자](#42-식별자)**

**[4.3 변수선언](#43-변수-선언)**

**[4.4 변수 선언의 실행 시점과 변수 호이스팅](#44-변수-선언의-실행-시점과-변수-호이스팅)**

**[4.5 값의 할당](#45-값의-할당)**

**[4.6 값의 재할당](#46-값의-재할당)**

**[4.7 식별자 네이밍 규칙](#47-식별자-네이밍-규칙)**

<br>

### [05 표현식과 문](#05-표현식과-문)

**[5.1 값](#51-값)**

**[5.2 리터럴](#52-리터럴)**

**[5.3 표현식](#53-표현식)**

**[5.4 문](#54-문)**

**[5.5 세미콜론과 세미콜론 자동 삽입 기능](#55-세미콜론과-세미콜론-자동-삽입-기능)**

**[5.6 표현식인 문과 표현식이 아닌 문](#56-표현식인-문과-표현식이-아닌-문)**

<br>

### [07 연산자 (Operator)](#07-연산자-operator)

**[7.1 산술 연산자](#72-할당-연산자)**

- [7.1.1 이항 산술 연산자](#711-이항-산술-연산자)

**[7.2 할당 연산자](#72-할당-연산자)**

**[7.3 비교 연산자](#73-비교-연산자)**

- [7.3.1 동등/일치 비교 연산자](#731-동등일치-비교-연산자)
- [7.3.2 대소 관계 비교 연산자](#732-대소-관계-비교-연산자)

**[7.4 삼항 조건 연산자 ( ? : .. : )](#74-삼항-조건-연산자)**

**[7.5 논리 연산자 ( && , || )](#75-논리-연산자)**

**[7.6 쉼표 연산자](#76-쉼표-연산자)**

**[7.7 그룹 연산자](#77-그룹-연산자)**

**[7.8 typeof 연산자](#78-typeof-연산자)**

**[7.9 지수 연산자](#79-지수-연산자)**

**[7.12 연산자 우선 순위](#712-연산자-우선-순위)**

**[7.13 연산자 결합 순서](#713-연산자-결합-순서)**


<br>

### [09 타입 변환과 단축 평가](#09-타입-변환과-단축-평가)

**[9.1 타입 변환이란?](#91-타입-변환이란)**

**[9.2 암묵적 타입 변환](#92-암묵적-타입-변환)**

- [9.2.1 문자열 타입으로 변환](#921-문자열-타입으로-변환)
- [9.2.2 숫자 타입으로 변환](#922-숫자-타입으로-변환)
- [9.2.3 불리언 타입으로 변환](#923-불리언-타입으로-변환)

**[9.3 명시적 타입 변환](#93-명시적-타입-변환)**

- [9.3.1 문자열 타입으로 변환](#931-문자열-타입으로-변환)
- [9.3.2 숫자 타입으로 변환](#932-숫자-타입으로-변환)
- [9.3.3 불리언 타입으로 변환](#933-불리언-타입으로-변환)

**[9.4 단축 평가](#94-단축-평가)**

- [9.4.1 논리 연산자를 사용한 단축 평가](#941-논리-연산자를-사용한-단축-평가)
- [9.4.2 옵셔널 체이닝 연산자 (?.)](#942-옵셔널-체이닝-연산자)
- [9.4.3 null 병합 연산자 (??)](#943-null-병합-연산자)

<br>


### [10 객체 리터럴](#10-객체-리터럴)

**[10.1 객체란?](#101-객체란)** 

**[10.2 객체 리터럴에 의한 객체 생성](#102-객체-리터럴에-의한-객체-생성)**

**[10.3 프로퍼티](#103-프로퍼티)**

**[10.4 메서드](#104-메서드)**

**[10.5 프로퍼티 접근](#105-프로퍼티-접근)**

**[10.6 프로퍼티 값 갱신](#106-프로퍼티-값-갱신)**

**[10.7 프로퍼티 동적 생성](#107-프로퍼티-동적-생성)**

**[10.8 프로퍼티 삭제](#108-프로퍼티-삭제)**

**[10.9 ES6에서 추가된 객체 리터럴의 확장 기능](#109-es6에서-추가된-객체-리터럴의-확장-기능)**

- [10.9.1 프로퍼티 축약 표현](#1091-프로퍼티-축약-표현)
- [10.9.2 계산된 프로퍼티 이름](#1092-계산된-프로퍼티-이름)
- [10.9.3 메서드 축약 표현](#1093-메서드-축약-표현)

<br>

### [27 배열](#27-배열)

**[27.1 배열이란?](#271-배열이란)** 

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

-  **<u>*null 병합 연산자*</u>**  : 좌항의 피연산자가 null 또는 undefined인 경우 우항의 피연산자를 반환하고, 그렇지 않으면 좌항의 피연산자를 반환한다

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

## 27.5  배열 요소의 참조

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

