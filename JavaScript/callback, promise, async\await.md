
### callback, promise, async/await 에 대해 설명해주세요.

먼저 `callback` 은 다른 함수에 인자로 전달된 함수를 이야기합니다.

이를 이용하면 함수의 로직이 끝난 뒤, 인자로 전달받은 함수를 실행시켜 그 실행 순서를 보장 할 수 있습니다.

하지만, 콜백을 연속적으로 사용하는 경우 콜백 헬이 발생하여 유지보수가 힘들어지는 경우가 생깁니다.

<br>

다음으로, `promise` 는 callback 대신 `.then` 을 이용합니다.

Promise 를 호출하면 콜백함수를 인자로 받을 수 있는데, 이 콜백 함수의 인자로 `resolve` 와 `reject` 를 받습니다.

만약 로직 정상 처리 시 `resolve` 를 이용해서 처리하고, 실패 시 `reject` 를 이용합니다.

그리고 Promise 는 세 가지 상태를 가지는데, 로직에 대한 처리가 되지 않은 상태를 `pending`, 정상 처리 되어 `resolve` 가 실행된 경우를 `fulfilled`, 실패 혹은 에러가 발생하여 `reject` 가 실행된 경우 `rejected` 라는 상태를 가집니다.

이 때 로직이 정상으로 처리된 경우 resolve 에서 반환된 값을 `.then` 에서 활용 할 수 있으며, 정상 처리가 아닌 경우 `.catch` 를 사용하여 reject 에서 반환된 값을 받게됩니다.

<br>

`async / await` 은 promise 를 더 편리하게 작성하게 해주는 문법입니다.

함수 앞에 `async` 를 사용하면 해당 함수는 promise 를 반환하게 됩니다.

`async` 내부에서는 `await` 을 사용 할 수 있는데, 이를 이용하면, promise 가 처리된 결과값을 변수에 저장 할 수 있게됩니다.

에러핸들링은 `try-catch` 문 를 사용하며 promise 가 정상처리 된 경우 `try` 의 로직을 실행하고, 에러가 발생한 경우는 `catch` 의 로직을 실행하게 됩니다.

최근 async 없이도 await 을 사용 할 수  top-level await 문법이 추가된 것으로 알고있습니다.

---

- async 함수도 promise 를 반환하므로, `.then`을 사용 할 수 있다.
- 콜백

```tsx
function fn (num, callback) {
  callback(num + 5)
}

fn(0, num => {
    fn(num, num => {
        fn(num, num => {
            fn(num, num => {
                console.log(num) // 20
            })
        })
    })
})
```

→ 가독성도 좋지 않거니와, 코드가 오른쪽으로 날아간다….

- 프로미스

```tsx
function fn2 (num) {
	return new Promise((resolve) => {
    resolve(num + 5)
  })
}

fn2(0)
  .then(res => fn2(res))
  .then(res => fn2(res))
  .then(res => fn2(res))
  .then(res => fn2(console.log(res))) // 20
  .catch(err => return err)
```

→ fulfilled 된 결과를 .then 을 이용하여 프로미스 체이닝하여 더 코드가 더 깔끔하고 가독성이 좋다.

- async / await

```tsx
function fn3 (num) {
	return new Promise((resolve) => {
    resolve(num + 5)
  })
}

async function asyncFn () {
  try {
    const a = await fn3(0)
    const b = await fn3(a)
    const c = await fn3(b)
    const d = await fn3(c)

    console.log(d) // 20
  }
  catch(err){
    return err
  }
}

asyncFn() // 20
```

→ await을 이용하여 변수에 결과값을 담아 사용하기 때문에 더 확장성에 장점을 가진다.

- top-level await

```tsx
function fn4 (num) {
	return new Promise((resolve) => {
    resolve(num + 5)
  })
}

const a = await fn4(0)
const b = await fn4(a)
const c = await fn4(b)
const d = await fn4(c)

console.log(d) // 20
```

→ async 필요없이 바로 변수에 프로미스의 결과값을 저장 할 수 있다.
