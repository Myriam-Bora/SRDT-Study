# 07 연산자 (Operator)

[TOC]



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

  `var x = 5;`

  `var result;`

  `result = x++; *//5 6 : 선할당 후증가*`

  `result = ++x; *//7 7 : 선증가 후할당*`

- 숫자 타입이 아닌 피연산자에 + 단항 연산자를 사용하면 피연산자를 숫자 타입으로 변환하여 반환한다.

  `var x = "5";`

  `console.log(+x); *// 1  : 문자열을 숫자로 타입 변환한다*`

  `console.log(x); *// "1" : 부수 효과는 없다*`

  

  `var y = true;`

  `console.log(+x); *// 1  : 불리언 값을 숫자로 타입 변환한다*`

  

  `var y = "hello";`

  `console.log(+x); *//NaN : 문자열을 숫자로 타입 변환할 수 없다*`

- 단항 연산자 - 는 피연산자의 부호를 반전한 값으로 반환한다

  `console.log(-(-10)); *// 10  : 부호를 반전한다*`

- 단항 연산자 + 와 마찬가지로, 숫자 타입이 아닌 피연산자에 - 단항 연산자를 사용하면 피연산자를 숫자 타입으로 변환하여 반환한다.

  `console.log(-"10"); *// -10 : 문자열을 숫자로 타입 변환한다*`

  

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

  

### <u>7.3.1 동등/일치 비교 연산자</u>

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
| 2        | new(매개변수 존재) ,  [ ]프로퍼티 접근, ( ) 함수호출 , ? (옵셔널 체이닝 연산자) |
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

  
