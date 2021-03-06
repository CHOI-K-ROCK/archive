### useState 를 사용하는 이유

먼저, 상태는 기존 상태를 직접적으로 변경해서는 안된다는 불변성을 가집니다.

그 이유는, 상태는 객체 형식의 데이터입니다.

리액트는 객체가 참조하는 주소의 변경을 추적하여 컴포넌트를 리렌더링하는데, 
상태 값을 직접 변경하는 경우 같은 참조 주소가 변경되지 않으므로 리렌더링이 이루어지지 않습니다.


하지만, `setState` 를 사용하는 경우, 새로운 객체를 만들어 상태에 저장하게 되고, 
참조 주소가 변경되면서 리액트가 이를 추적하고 리렌더링 할 수 있게됩니다.

---
- 상태는 불변성을 가진다 -> 상태를 직접 변경하면 안된다.
- 상태는 객체 형태로, 주소값을 가지는 데이터이다. (참조자료형)
- 리액트는 상태의 참조 주소 변경을 추적하여 리렌더링 한다.
- setState 는 새로운 객체를 만들어 상태를 변경시킨다.(새로운 참조 주소)
- 상태는 클로저를 활용한다.
- 예시
```js
const [state, setState] = useState('초기값');
setState('변경될 값')

const useState = (초기값) => {
  let 기본값 = 초기값;
  
  const state = () => 기본값;
  const setState = (변경값) => {
    기본값 = 변경값;
  };
  
  return [state, setState];
};
// 결과적으로 리턴되는 것은 `기본값`
//호출되는 함수에 따라 기본값을 반환할지, 아니면 변경할지가 정해진다.
```
