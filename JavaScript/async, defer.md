###  async, defer

일반적으로 HTML이 파싱될 때 `script` 태그를 만나게 되면 HTML 파싱을 중단하고, `script` 파일을 로드, 실행 한 뒤 HTML 파싱을 진행합니다.

이 때 `async` 키워드를 사용하는 경우, `script` 의 로드가 HTML 파싱과 동시에 이루어지고, 로드가 끝난 후 파싱을 중단하고 `script` 를 실행합니다.

`defer` 를 함께 작성하는 경우에는 `script` 의 로드가 HTML 파싱과 동시에 이루어지지만, HTML 파싱이 종료된 뒤 `script` 가 실행됩니다.

---
- async 는 비동기적으로 동작한다.
  - 먼저 로드 된 스크립트가 먼저 실행된다.(실행순서를 보장하지 않는다.)
  - 다른 스크립트에 의존성이 있는 경우라면 async 를 피하는 것이 좋다.
- defer 는 동기적으로 동작한다.
  - 먼저 작성된 스크립트가 먼저 실행된다.(실행순서를 보장한다.) 


> 참고
> https://wormwlrm.github.io/2021/03/01/Async-Defer-Attributes-of-Script-Tag.html
