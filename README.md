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

## hooks
1.) useState
```javascript
import React,{useState} from "react";
let [name,setName] = useState("sidd")
```
2.) 

