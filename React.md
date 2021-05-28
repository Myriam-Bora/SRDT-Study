- render 함수는 순수 함수로 작성 한다
  - 순수함수 
    - 부수적인 효과 X
    - 동일한 인자가 들어갈 경우 항상 같은 값이 나와야한다
    - return 값으로만 소통한다
  - 랜덤 함수 사용 X  (날짜함수 등)
  - 외부 상태 변경 X
- state는 불변 변수로 관리한다



## 바벨

- 자바스크립트 코드를 변환해 주는 컴파일러
- 최진 자바스크립트 문법을 지원하지 않는 환경에서도 최신 문법 사용 가능
- 코드에서 주석을 제거나허나 코드를 압축하는 용도
- 리액트에서는 JSX문법을 createElement 함수를 호출하는 코드로 변환
  - JSX는 순수 자바스크립트가 아니기 때문에 브라우저에서 실행이 되지 않는다

------

## 웹팩

- 모듈 시스템 (ESM, commonJS) 을 사용하게 해준다
  - ex) export default from as
  - 웹팩이 없으면 <script> 태그를 써야한다
  - default를 통해 export를 한 경우 : { } 중괄호를 통하여 import
  - default  없이 export 한 경우 : 중괄호 없이 임포트
  - as : 중괄호를 통해 통해 import한 것을 이름변경 가능
- 자바스크립트 압축
- JS에서 CSS,JSON,텍스트 파일 등을 일반 모듈처럼 불러오기
- 사용되지 않는 코드 제거

------

## create-react-app

- 리액트 개발 환경을 직접 구축하기 위한 지식과 노력이 상당히 필요한데, 이걸 자동으로 구축해주는 패키지
  - 웹팩 , 바벨, eslint 등

------

## React.Fragment

- ​	return ( <div></div>)  처럼 div가 추가 되는걸 원하지 않을 때
- 예) <React.Fragment></React.Fragment>
- 예2) <> </>

------

## Portal

- 멀리 떨어린 엘리먼트에 컴퍼넌트 삽입
- 주로 모달에 사용
- 첫번째 매개변수 : 넣고 깊은 요소
- 두번째 매개변수 : 추가하고자 하는 HTML 요소

------

## React.StrictMode

- 애플리케이션 내의 잠재적인 문제를 알아내기 위한 도구
- Fragment와 같이 UI를 렌더링 하지 않고, 자손들에 대한 부가적인 검사와 경고를 활성화
- 개발 모드에서만 활성화 되기 때문에 빌드에서를 영향을 끼치지 않는다
- 하는 일
  - 안전하지 않은 생명주기를 사용하는 컴포넌트 발견
  - 레거시 문자열 ref 사용에 대한 경고
  - 권장되지 않는 findDOMNode 사용에 대한 경고
  - 예상치 못한 부작용 검사
  - 레거시 context API 검사

------

## 성능최적화

- 컴포넌트가 느려지는 원인
  - 자신이 전달받은 props가 변경 될 때
  - 자신의 state 가 바뀔 때
  - 부모 컴포넌트가 리렌더링 될 때
  - forceUpdate 함수가 실행 될 때

- React.memo
  - props가 바뀌지 않았다면 리렌더링 하지 않게 방지 
- useSelector / useDispatch 대신에 connect 사용
  - connect 를 사용하여 컨테이너 컴포넌트를 만들 경우, 해당 컨테이너 컴포넌트의 부모 컴포넌트가 리렌더링 될 때 해당 컨테이너 컴포넌트의  props가 바뀌지 않아싸면 리렌더링이 자동으로 방지 된다
  - 반면, useSelector를 사용하여 리덕스 상태를 조회했을 때는 최적화 작업이 자동이 되지 않지만 React.memo를 사용하면 동일한 최적화가 가능

- useCallBack
  - 만들었던 함수를 재사용 할 수 있다
  - 첫번째 파라미터 : 생성하고 싶은 함수
  - 두번째 파라미터 : 어떤 값이 바뀌었을 때 함수를 새로 생성해야 하는 지 명시 (배열)
- useSelector의 selector 함수는 action dispatch가 일어나면 최소1회 최대 3회까지 호출 될 수 있다
  - 원인1 : action이 dispatch 되서
    - useSelector 마다 리덕스 스토어를 subscribe 하기 때문에
  - 원인2 : 렌더링 시 store가 달라져서
  - 원인3: StricMode로 렌더링이 한 번 더
    - <React.StrictMode> : 렌더링 강제로 2번 실행
  - 해결 방법 
    -  useSelector 호출 시 함수를 생성하지 않고 useCallBack을 이용
    -  selector 함수를 컴포넌트 밖에서 선언한 후 참조

------

## Hook

- 리액트의 state는 비동기로 처리하면서 배치(batch) 로 처리한다
- 즉, 비동기요소를 한번에 모아서 렌더링
- 지켜야할 규칙
  - 하나의 컴포넌트에서 훅을 호출하는 순서는 같아야한다

------

## Context API

- 부모컴포넌트 에게서 멀리 떨어진 자식 컴포넌트에게 props 전달하기

![image-20210528134531351](C:\Users\bora_lee\AppData\Roaming\Typora\typora-user-images\image-20210528134531351.png)

- 주의사항
  - 부모 컴포넌트에서 state에 담겨진 props값이 바뀌면 자식 컴포넌트들도 리렌더링이 된다

------

## ref

- 부모에서 자식으로 props를 통해  ref를 전달하는 방법
  - 1

```javascript
<ParentComponent buttonRef={buttonRef}>
 	<Button buttonRef={buttonRef}/>
</ParentComponent>
```

- 아래 코드처럼 직관적인 이름 (ref)로 전달하고자 하는 경우, ref를 사용하면 리액트가 내부적으로 처리해버리기 때문에 다른 방법이 필요하다

```javascript
<Button ref={buttonRef}/>
```

- 2 .React.forwardRef 함수를 호출

```javascript
<ParentComponent buttonRef={buttonRef}>
 	<Button ref={buttonRef}/>
</ParentComponent>

const Button = React.forwardRef(function {{onClick}, ref}{
	return (
		<button onClick={onClick} ref={ref}/>
	)
})
```

- useRef를 사용하지 않고 ref 속성에 함수를 입력
  - 해당하는 요소가 생성되거나 사라질 때 한 번씩 호출 된다
  - 생성 될 때 : 해당하는 레퍼런스를 넘긴다
  - 사라질 때 : null
- 갯수가 가변적인 div에 ref를 다루고 싶을 때

```javascript
const boxListRef = useRef({});

return(
	...
    {box_list.map(item=>{
     	<div
     		key={item.id}
    		ref={ref => {boxListRef.current[item.id] = ref}}
		>{${item.id}}</div>
    })}
)
```

- ref 사용시 주의할 점
  - 컴포넌트가 생성되어도 ref 객체의 current 속성이 없을 수 있다

```javascript
return(
	<div>
    	{showText && <input type="text" ref={inpuRef}/>} //조건부 렌더링
    	<button onClick={()=> inputRef.current.focus()}/> //조건이 맞지 않을 경우 current 속성이 없음
    </div>
)
```

- 조건부 렌더링 컴포넌트 일 때 , 사용된 요소 ref객체는 current 속성을 검사하는 코드가 필요

```javascript
return(
	<div>
    	{showText && <input type="text" ref={inpuRef}/>} //조건부 렌더링
    	<button onClick={()=> inputRef.current && inputRef.current.focus()}/> //조건 추가
    </div>
)
```

------

## 내장 Hook

- useMemo :계산량이 많은 함수의 반환값을 재활용
-  useCallBack : useMemo와 유사.  함수 재활용에 특화
  - 부모컴포넌트에서 함수를 자식에게 props로 전달한 경우, 부모의 상태가 바뀔 때 마다  자식이 리렌더링 되는 문제가 있다
  - 이때 useCallBack을 사용하여 리렌더링 방지 (지정한 값만 변경될 때마다 렌더링 할 수 있게 설정 가능)
- useReducer : action에 따라 상태값을 바꿀 수 있음
  - Context API와 함께 사용하여 자식컴포넌트에서 부모 상태값을 변경 할 수 있는 코드를 쓸 수 있음(리덕스와 유사) 
- useImperativeHandle : getter , setter 역할
  - 자식 컴포넌트가 제공한 함수를 부모에서 호출할 수 있음
  - forwardRef도 함께 사용하여 자식이 부모에게 ref를 전달

![image-20210528162717456](C:\Users\bora_lee\AppData\Roaming\Typora\typora-user-images\image-20210528162717456.png)

- useLayoutEffect : useEffect와 유사
  - 성능상 이슈가 있어 useEffect 사용을 권장
  - 사용하는 경우는
    - 리액트가 렌더링을 하고 실제 돔에 반영은 했지만 브라우저가 화면을 그리기전에 실행 (동기).한 후 렌더링 직후에 돔 요소의 값을 읽어들이는 경우
    - 조건에 따라 컴포넌트를 다시 렌더링 하고 싶은 경우
