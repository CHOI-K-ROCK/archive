### state 와 props 의 차이

`state` 는 컴포넌트가 생성하고 관리하는 일종의 변수를 뜻 합니다. 

변경 될 수 있는 데이터를 객체의 형태로 저장하며, 갱신함수를 통해 상태가 변경되면 객체 주소의 변경을 추적하여 컴포넌트를 리렌더링 합니다.

`props` 는 부모 컴포넌트가 자식 컴포넌트로 전달하는 데이터로써, 변경 할 수 없는 읽기 전용 데이터입니다.

---

### state
- 컴포넌트 내부에서 생성한다.
- 컴포넌트에서 관리된다
- 갱신함수를 통해 변경이 가능하다
- 변경시 리렌더링 된다.

### props
- 부모 컴포넌트로부터 전달받는다.
- 읽기전용 데이터이다.
  - 변경 될 수 없다.
