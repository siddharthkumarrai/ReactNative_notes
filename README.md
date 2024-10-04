cmd to start emulator on real device without usb cable
1.) C:\Users\siddh\AppData\Local\Android\Sdk\platform-tools> open cmd
2.) adb devices
3.) adb tcpip 5555
4.) adb connect 192.168.1.2:43683

for screen copy
scrcpy -s 192.168.1.2:46135

# ReactNative_notes
### install react-native new project
```javascript
npx react-native init basicreactnative
```
### First program
> App.tsx
```javascript
import React from "react";
import {Text, View } from "react-native";
const  App = () => {
  return(
    <View>
    <Text style={{color:"red",fontSize:40}}>hii i am don </Text>
    <Button title="press here" onPress={function()()} color={"blue"} />
    </View>
  )
}
export default App;
```
### React-Native components
1.) SafeAreaView, View, Text
- SafeAreaview : It prevent overlapping
- View : Just like a div
- Text : string text on display

```javascript
import {Text, View, SafeAreaView } from "react-native";
    <SafeAreaView>
    <View>
    <Text> hii i am don </Text>
    </View>
    </SafeAreaView>
```


2.) StyleSheet
```javascript
import { StyleSheet } from 'react-native'

    <View style={styles.container} >
    <Text> hii i am don </Text>
    </View>

const styles = StyleSheet.create({
  container:{
    flex:1
  }
})
```
3.) ScrollView
```javascript
import { ScrollView } from 'react-native'
<ScrollView horizontal={true} style={styles.cardsContainer} >
    <View style={styles.container} >
    <Text> hii i am don </Text>
    </View>
</ScrollView>
```
4.) Image
```javascript
<Image
source={{
    uri: 'https://something'
}}
style={styles.cardImage}
/>
```
5.) Linking
```javascript
import { Linking } from 'react-native'

## hooks
1.) useColorScheme
```javascript
let isDarkMode = useColorScheme() === 'dark'
<Text style={isDarkMode? styles.whiteText: styles.blackText}> hii i am don </Text>
```

2.) useState
```javascript
import React,{useState} from "react";
let [name,setName] = useState("sidd")
```

3.) 

