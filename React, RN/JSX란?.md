### JSX 란?
JSX는 React에서 사용되는 자바스크립트의 확장 문법입니다.

JS와 마크업 언어가 합쳐진 형태이며, 브라우저에서 바로 읽을 수 없고 바벨을 통해 자바스크립트로 컴파일되어 읽힙니다.

특징으로는, 반환하는 요소는 반드시 부모 요소에 감싸진 형태여야 하며, 닫힌 태그의 경우 self-closing 태그를 반드시 작성해야 합니다.

JSX 내부에서 중괄호를 사용하여 JS 표현식을 사용할 수 있으며, 

표현식 내부에서 조건부 렌더링을 사용하기 위해서는 조건문이 아닌 `삼항연산자` 혹은 `AND 연산자(&&)`를 사용해야합니다.

요소의 class 는 `className` 으로 작성하고, 인라인 스타일은 객체의 형식으로 전달하며, 이때 속성 이름은 camel-case 로 작성합니다.

---

- 요소를 감쌀 때 fragment 문법을 사용 할 수 있다.
```jsx
return (
  <fragment>
    <p>hello</p>
    <p>react</p>
  </fragment>
)

// 혹은 
return (
  <>
    <p>hello</p>
    <p>react</p>
  </>
)
```
  -> 이렇게 작성된 fragment 는 브라우저에서 별도의 태그로 나타나지 않는다.
- `<br>`, `<img>` 등의 닫힌태그는 반드시 self-closing 한다.(리액트 컴포넌트도 동일)
  - `<br />`,`<img />`
- 클래스 작성과 인라인 스타일 작성
```jsx
export default function App () {
  // 객체로 작성
  const inlineStyle = {
    width : "100px",
    height : "100px",
    backgroundColor : "#ffd"
  }
  
  return (
    <div className="클래스 이름" style={inlineStyle}> 얏호~ </div>
  )
}
```
