### 클로저란?

클로저는 어떤 함수가 중첩되어 작성되어 있을 때 외부함수의 변수에 접근 가능한 내부함수를 이야기합니다.

외부함수의 실행이 끝나더라도, 내부함수가 외부함수의 변수에 접근 할 수 있기 때문에 데이터 보존이 가능하다는 특징을 가지고 있습니다.

이는 자바스크립트가 상위 스코프를 결정 할 때 함수가 선언된 어휘적 환경을 참조하기 때문입니다.

내부함수가 자신이 선언되었을 때의 어휘적 환경을 저장하고 있으므로 외부함수가 종료 되더라도 변수에 접근 할 수 있는 것 입니다.

또한, 함수 내부에 선언된 변수는 스코프 규칙에 의해 직접적으로 변경 될 수 없으며, 내부 함수를 이용해야만 변경 할 수 있습니다.

이를 은닉화, 캡슐화라고 합니다.

---

### 렉시컬 스코프

- 함수가 선언된 환경을 저장하는 스코프
- JS는 이를 기반으로 상위스코프를 결정한다. → 즉, 선언된 곳을 기준으로 상위스코프를 결정한다.
- 렉시컬 스코프 예시

```tsx
let fruit = 'apple';

function fn() {
    let fruit = 'banana';
    fn2();
};

function fn2() {
    console.log(fruit);
};

fn(); // 'apple'
```

→ 호출(fn)이 아닌 선언된 곳(global)을 기준으로 값을 참조한다.

- 클로저 예시

```tsx
const fruit = 'apple';

function outer() {
  const fruit = 'banana';

  return function inner() {
    console.log(fruit);
  };
};

const fn = outer();

fn(); // 'banana'
// 함수 inner 를 반환하며, 호출이 아닌 선언을 기준으로 상위 스코프를 탐색한다.
```

→ 저장된 렉시컬 스코프를 이용하여 내부함수의 변수에 접근한다.