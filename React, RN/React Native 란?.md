### React Native 란?

리액트 네이티브는 리액트 문법을 기반으로 모바일 네이티브 앱을 만들 수 있게해주는 자바스크립트 라이브러리입니다.

네이티브 앱으로 컴파일 되기 때문에 웹뷰를 사용한 하이브리드 앱보다 때문에 성능에서 이점을 가집니다.

JSX 문법을 사용하는 것은 동일하지만, HTML 문법이 아닌, 자체 컴포넌트를 사용하며, 

스타일의 경우 기존 CSS 와 문법적 차이가 존재하며, Style props 를 통해 전달받는다는 차이점이 있습니다.

---
- 스타일을 객체의 형식으로 전달하며, Camel-case를 사용하는 것은 JSX와 유사하나, 속성값의 단위를 문자열이 아닌 숫자로 입력한다.
  - 즉, 단위를 작성하지 않음.
- 이 때, 객체를 전달하거나, 인라인으로 작성 할 수 있으며, 여러 스타일을 적용할 때는 배열을 이용한다.
  - `[스타일 객체, {스타일}]`, `[{스타일}, 스타일 객체]`  
  - 뒤에 작성된 스타일이 우선순위가 높다.

```jsx
import React from "react";
import { StyleSheet, View, Text } from "react-native";

export default App () {
  <View>
    <View style={style.box} />
    <View style={width : 100, height : 100, backgroundColor : "red"} />
  </View>
}

const style = StyleSheet.create({
  box = {
    width : 100,
    height : 100,
    backgroundColor : "red"
  }
});
```
