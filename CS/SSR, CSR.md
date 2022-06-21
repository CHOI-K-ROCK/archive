### SSR 과 CSR 의 차이

SSR은 Server Side Rendering 의 약자로, 페이지의 렌더링이 서버에서 이루어지는 것을 이야기합니다.

렌더링에 대한 준비가 이미 되어있기 때문에 첫 화면이 표시되는 시간이 빠르고, 

모든 컨텐츠가 문서에 포함되어있기 때문에 SEO 에 대한 장점이 있습니다.

하지만, 페이지 이동마다 전체 페이지를 서버에서 새로 불러와야 하며, 서버의 부담이 크다는 단점이 있습니다.
<br><br>

CSR 은 Client Side Rendering 의 약자로, 페이지의 렌더링이 클라이언트에서 이루어지는 것을 이야기합니다.

클라이언트는 렌더링에 필요한 모든 JS 파일을 전달 받습니다.

페이지 이동시 서버에서 받은 데이터를 준비된 JS 파일을 이용하여 렌더링하므로, 반응속도가 빠르다는 장점이 있습니다.

하지만, 하지만 렌더링 되기전의 파일이 비어있으므로 SEO에 불리하며,

JS 파일이 큰 경우 초기 로딩의 시간이 길어진다는 단점이 있습니다.

---

### SSR
- 필요한 페이지를 완전하게 렌더링해서 전달함.
- 새로운 페이지를 전부 처음부터 새로 렌더링해서 전달해줌
- MPA(Multi Page Application) 에 유리

### CSR
- 렌더링에 필요한 모든 JS 파일과 데이터를 전달함.
- 새로운 페이지에 필요한 데이터를 전달하고, 클라이언트가 해당 데이터를 기반으로 페이지를 렌더링함.
- SPA(Single Page Application) 에 유리