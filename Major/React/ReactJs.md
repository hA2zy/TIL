`npx create-react-app my-app`

React 설치 명령어

`npm start`

React 실행 명령어

- **import React from ‘react’**
    
    이 JSX 문법을 자바스크립트로 변환시킬 때 JSX transformer를 사용해 JSX로 작성된 React 메소드를 변환
    
    ## 그럼 왜 생략을 할까?
    
    이는 작성하고 있는 컴포넌트가 상위 컴포넌트 인지 하위 컴포넌트 인지 파악하고 만약 상위 컴포넌트에 `import React from ‘react’`가 작성되었다면 하위에서는 생략해도 작동이 된다.
    
    물론 생략하지 않아도 작동하는데에는 아무런 지장이 없다. 추후 웹팩을 통해 최적화된 코드로 작성되므로 중복에 대한 비효율성은 걱정하지 않아도 된다.
    

- **className, 변수를 html에 넣는 방법, JSX에 style을 넣는 법**
    
    # className
    
    className는 HTML에서 class를 주는 것이다.
    
    class주는 것을 JSX에서 className으로 준다.
    
    ```jsx
    function Btn() {
      return (
        <>
          <h1 className="ex"> 이건 제목이야!!!</h1>
        </>
      );
    }
    ```
    
    <h4>의 className은 ex이다.
    
    # 변수를 html에 꽃아넣기
    
    변수를 html에 넣을 수 있는 방법은 document.querySelector를 사용해서 할 수 있다.
    
    하지만 여기서 또 다른 쉬운 방법이 있는데 {}를 사용하는 것이다.
    
    ```jsx
    function Btn() {
      let exam = "예시";
      return (
        <>
          <h1></h1>
        </>
      );
    }
    ```
    
    들어가서 화면을 보면 아무것도 뜨지 않지만 <h1>{exam}</h1>으로 바꾸게 되면 예시라는 글이 뜨게 된다.
    
    ```jsx
    function Btn() {
      let exam = "예시";
      return (
        <>
          <h1 id="{exam}">{exam}</h1>
        </>
      );
    }
    ```
    
    id를 저런 식으로 넣게 되면 id가 예시로 바뀌는 것을 볼 수 있다.
    
    # JSX에서 style을 넣는 방법
    
    JSX에서 style을 넣고 싶으면 css파일을 만들어서 하던가 style={{스타명:’값’}}을 입력하면 된다.
    
    ```jsx
    function Btn() {
      return (
        <>
          <h1 style={{color:'red', fontSize:'11PX'}}> 이건 제목이야!!!</h1>
        </>
      );
    }
    ```
    
    이런 식으로 만들면 color이랑 fontSize를 설정할 수 있다.
    
- **state를 쓰면 좋은 이유**
    - state를 사용하는 이유는 다른 변수들을 사용을 하면
    - 화면에 바로바로 나오지 않지만
    - state는 바로바로 랜더링이 된다는 장점이 있다.(단, 너무 많이 사용X)
    
    자료를 저장하고 싶을 때에는 변수를 사용해서 저장을 할 수 있다.
    
    useState를 사용하면 간단하게 할 수 있다.
    
    ```jsx
    let [a, b] = useState('안녕하세요');
    ```
    
    useState를 엔터치면 위에 `import (useState} from ‘react’;`처럼 생겨난다.
    
    저 코드처럼 state를 만들어낸다.
    
    a는 변수 이름
    
    b는 state 변경을 도와주는 함수
    
    useState 괄호 안에 있는 것은 state에 보관을 하고 있는 자료이다.
    
    ```jsx
    <button
            onClick={function () {
              set변수("르세라핌");
            }}
          >
            버튼ㅋ
          </button>
    ```
    
    함수 실행은 변수를 쓴다음에 버튼이 눌렸을 때 르세라핌으로 바뀌도록 만들어 놓은 것이다.
    
    ```jsx
    function Btn() {
      const [변수, set변수] = useState("르세라핌");
      return (
        <>
          <h1>{변수}</h1>
        </>
      );
    }
    ```
    
    저러면 변수의 이름이 바뀐다.
    
    ---
    
    # 참고
    
    Destructuring 문법
    
    ```jsx
    let num = [1, 2];
    let a = num[0];
    let b = num[1];
    ```
    
    이런 식으로 쓰면 너무 길다.
    
    ```jsx
    let [a, b] = [1, 2];
    ```
    
    이런 식으로 쓰면 저기 위에 있는 식과 같아진다.
    
- ****버튼에 지리는 기능만들기****
    
    `const [변수, set변수] = useState(['LESSERAFIM', '르세라핌','귀여운 핌둥이들']);`
    
    이런 식으로 배열을 사용을 할 수 있다.
    
    `<h1>{변수[1]}</h1>`배열을 꺼내듯이 꺼내면 <h1>에는 **르세라핌**이 들어가게 된다.
    
    ---
    
    state는 등호를 사용을 하면 안바뀐다.
    
    ```jsx
    function Btn() {
      const [변수, set변수] = useState(0);
      return (
        <>
          <h1>
            누른 횟수{" "}
            <button
              onClick={() => {
                set변수(변수 + 1);
              }}
            >
              Click me{" "}
            </button>
            {변수}
          </h1>
        </>
      );
    }
    ```
    
    이 코드는 버튼을 누를 때마다 1이 증가하는 코드이다.
    
- **컴포넌트 만들기**
    
    컴포넌트는 React 애플리케이션의 구성 요소로, UI의 작은 독립적인 조각을 나타낸다.
    
    각 컴포넌트는 자체적인 상태와 렌더링 로직을 가지며, 이들은 조합하여 복잡한 UI를 구축가능
    
    <aside>
    💡 컴포넌트를 사용하면 코드 재사용성과 유지보수성이 향상되며, 애플리케이션의 다양한 부분을 모듈화하고 구조화하는 데 도움을 준다.
    
    </aside>
    
    대표적인 종류로는 함수 컴포넌트랑 클래스 컴포넌트가 있다.
    
    ```jsx
    function App() {
    	return (
    		<></>
    	)
    }
    ```
    
    함수 컴포넌트
    
    ```jsx
    class App extends Component {
    	render() {
    		return(
    		<></>
    		)
    	}
    }
    ```
    
    클래스 컴포넌트
    
    컴포넌트 종류로는 대표적으로 함수 컴포넌트랑 클래스 컴포넌트가 존재한다.
    
    처음 React를 실행했을 때 App.js에 있는 함수가 함수 컴포넌트이다.
    
    <aside>
    ⚠️ 컴포넌트 이름은 맨 앞글자를 대문자로 해서 작성한다.
    
    </aside>
    
- **배포하기**
    
    npm run build를 하면 build라는 파일이 생기는데 이 파일로 배포를 한다.
    
    npm install -g serve라는 명령어를 하게 되면
    
    언제 어디서나 자신의 컴퓨터에서 serve라는 명령어를 통해 웹서버를 설치 할 수 있다.
    
    npm serve -s build 실행
    
- **props**
    
    컴포넌트를 사용할 경우 내가 짠 컴포넌트가 똑같이 계속 나온다.
    
    ```jsx
    //App.js
    function App() {
      return (
        <>
        <Example/> // 컴포넌트 A
    		<Example/> // 컴포넌트 B
        </>
      );
    }
    ```
    
    저기서 A랑 B는 똑같은 결과만 항상 보여준다.
    
    이러한 문제점을 막기 위해서 props를 사용하는 것이다.
    
    ```jsx
    //App.js
    function App() {
      return (
        <>
        <Example name="World!"/>
        </>
      );
    }
    ```
    
    이런식으로 Example로 name을 보내면 Example.js에서 저 props를 받으면 된다.
    
    ```jsx
    //Example/js
    function Example (props) {
        return(
            <>
            <h1>Hello {props.name}</h1>
            </>
        )
    }
    
    export default Example
    ```
    
    저기서 props를 받은 뒤에 {props.자신이 쓴 속성 이름}을 쓰면 화면에 나오게 된다.
    
- **state 소개**
    
    state는 props랑 같이 봐야한다.
    
    두 개의 차이점을 통해서 state 또는 props를 더 잘 이해할 수 있다.
    
    컴포넌트에서 기본적인 동작을 마음대로 바꾸고 싶을 경우에 props를 사용한다.
    
    그래서 사용자는 컴포넌트를 직접 조작을 할 수 있게 되었다.
    
    즉, props는 사용자나 구현자에게는 중요한 정보이다.
    
    하지만 state는 사용자가 알 필요도 없다.
    
    state는 컴포넌트 내부적으로 작동해서 사용하는 것들이다.
    
    <aside>
    💡 리엑트가 컴포넌트를 만들고, 컴포넌트는 좋은 부품(?)이 되기 위해서는 외부의 정보를 가져오는 props랑 props에 따라서 컴포넌트를 실제로 구현하는 내부의 state라는 정보가 철저하게 분리가 되어 있어야 한다.
    
    </aside>
    
- async와 await
    - `async`와 `await`은 프라미스를 좀 더 편리하게 사용하게 도와주는 것이다.
    
    ## async
    
    먼저 `async`는 function 앞에 위치한다.
    
    ```jsx
    async function f () {
    	return 1;
    }
    // ============== 화살표 함수 ==============
    const f = async () => {
    	return 1;
    }
    ```
    
    <aside>
    💡 function 앞에 async가 붙으면서 항상 프라미스를 반환한다.
    
    </aside>
    
    프라미스가 아닌 값을 반환을 하더라도 이행 상태의 **프라미스로 값을 감싸 이행된 프라미스가 반환되도록 한다.**
    
    ```jsx
    async function f() {
      return 1;
    }
    
    f().then(alert); // 1
    ```
    
    명시적으로 프라미스를 반환하는 것도 가능한데, 결과는 동일하다.
    
    ```jsx
    async function f() {
      return Promise.resolve(1);
    }
    
    f().then(alert); // 1
    ```
    
    ## await
    
    `await` 문법은 밑의 코드와 같다.
    
    ```jsx
    // await는 async 함수 안에서만 동작합니다.
    let value = await promise;
    ```
    
    자바스크립트는 `await` 키워드를 만나면 프라미스가 처리될 때까지 기다린다.
    
    ```jsx
    async function f() {
    
      let promise = new Promise((resolve, reject) => {
        setTimeout(() => resolve("완료!"), 1000)
      });
    
      **let result = await promise; // 프라미스가 이행될 때까지 기다림 (*)**
    
      alert(result); // "완료!"
    }
    
    f();
    ```
    
    함수를 호출하고 함수 본문이 실행되는 도중에 `(*)`로 표시한 줄에서 실행이 잠시 **중단**이 되었다가 프라미스가 처리되면 실행이 재개된다.
    
    `await`는 말 그대로 프라미스가 처리될 때까지 함수 실행을 기다리게 만든다.
    
    프라미스가 처리되면 그 결과와 함께 실행이 재개된다.
    
    프라미스가 처리되길 기다리는 동안엔 엔진이 다른 일(다른 스크립트를 실행, 이벤트 처리 등)을 할 수 있기 때문에, CPU 리소스가 낭비되지 않는다.
    
    `await`은 `promise.then`보다 더 세련되게 프라미스의 `result`값을 얻을 수 있게 해준다.
    
    <aside>
    💡 일반 함수에는 await을 사용할 수 없다.
    async 함수가 아닌데 사용을 하게 된다면 문법 에러가 발생하게 된다.
    
    </aside>
    

## this란?

- this는 자신이 속한 객체 또는 자신이 생성할 인스턴스를 가리키는 자기 참조 변수이다.
- his를 통해 자신이 속한 객체 또는 자신이 생성할 인스턴스의 프로퍼티나 메서드를 참조할 수 있다.

> ERROR은 에러라 중요
WARNING는 무시 가능

화면 크기 전체 너비가 100vw
화면 크기 전체 높이가 100vh

CSS를 연동하고 싶으면 **`import ‘./style.css/’`**으로 쓰면 된다.

return안에는 **무조건 하나의 태그로 시작을 해서 하나의 태그로 끝**이 나야한다.
두개의 태그를 쓰고 싶으면 <></>를 써서 저 태그 안에 넣어서 쓰면 된다.
>