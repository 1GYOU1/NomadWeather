## #2 WEATHER APP

### #2.1 The Rules of Native

- div 대신 view 태그 사용하며 import 해야함.
- 모든 텍스트는 text component 안에 있어야 함.
    - 브라우저가 아니기 때문에 h1, p, span 태그 등 사용 X
- StyleSheet.create를 쓰거나 object 만들거나, 태그 자체에 style 주기
    - StyleSheet.create 사용 또는 태그 자체에 스타일 줄때만 자동 완성 사용가능
- 웹에서 쓰던 css를 모두 쓸 수 없음.

nomad-weather/App.js
```js
import { StatusBar } from 'expo-status-bar';// 최상단 상태 바(시간, 와이파이, 배터리 등)
import { StyleSheet, Text, View } from 'react-native';

export default function App() {
  return (
    <View style={styles.container}>
      <Text style={styles.text}>Hello</Text>
      <StatusBar style="dark" />
    </View>
  );
}

const styles = StyleSheet.create({
  container: {
    flex: 1,
    backgroundColor: "white",
    alignItems: 'center',
    justifyContent: 'center',
  },
  text: {
    fontSize: 28,
    color: "black",
  },
});
```

<br>

### style 작성 방법
1. 상단 App.js에 쓰인 바와 같음. StyleSheet.create 사용
- 자동 완성 기능 사용 가능

<br>

2. 태그에 style 적용 
- 자동 완성 기능 사용 가능

```js
export default function App() {
  return (
    <View style={{
        flex: 1,
        backgroundColor: "white",
        alignItems: 'center',
        justifyContent: 'center'
    }}>
      <Text style={{
        fontSize: 28,
        color: "black"
      }}
        >
        Hello</Text>
      <StatusBar style="dark" />
    </View>
  );
}
```

<br>

3. StyleSheet.create 사용 X
- 자동 완성 기능 X
```js
const styles = {
  container: {
    flex: 1,
    backgroundColor: "white",
    alignItems: 'center',
    justifyContent: 'center',
  },
  text: {
    fontSize: 28,
    color: "black",
  },
};
```

<br>

### #2.3 Third Party Packages

react-native component와 Api

component
- 화면에 렌더링할 항목
- return 안에 있는 것
- ex) < view />
- https://reactnative.dev/docs/components-and-apis

api
- 자바스크립트 코드
- ex) Vibration 휴대폰 진동 기능
- https://reactnative.dev/docs/accessibilityinfo

Expo SDK
- Expo 팀에서 자체적으로 packages와 apis를 만듬
- React native packages를 찾을 수 없다면 Expo Packages 또는 Api 쓰면 됨
- https://docs.expo.dev/versions/latest/

<br>

### #2.4 Layout System

- 모든 view는 flex container
- flexDirection의 기본 값은 column
- 부모 flex box를 기준으로 children box의 비율을 정할 수 있음.

```js
import React from "react";
import { View } from "react-native";

export default function App() {
  return (
    <View style={{ flex: 1, flexDirection: "row" }}>
      <View style={{ flex: 1, backgroundColor: "lightpink" }}></View>
      <View style={{ flex: 1, backgroundColor: "lemonchiffon" }}></View>
      <View style={{ flex: 1, backgroundColor: "lavender" }}></View>
    </View>
  );
}
```