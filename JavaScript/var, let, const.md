### var, let, const

var, let, const 모두 변수를 선언하는 키워드입니다.

이들의 차이는, var 는 함수 스코프를 가지지만, let, const 는 블록 스코프를 가집니다.

var, let 은 재할당이 가능하지만, const는 재할당이 불가능합니다.

var 는 선언과 초기화가 동시에 이루어지지만, let, const 는 선언만 이루어집니다.

---

- let, const 는 ES6 이후에 추가된 문법이다.
- 변수의 선언은 3단계로 이루어진다.
  - 선언 -> 초기화 -> 할당
- var 는 선언과 동시에 undefind 로 초기화 된다.
  - 그렇기 때문에 var 변수가 호이스팅되어 undefind 를 표시 할 수 있음.
