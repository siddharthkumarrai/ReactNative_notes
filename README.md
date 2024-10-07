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
5.) Linking and TouchableOpacity
```javascript
import { Linking, TouchableOpacity } from 'react-native'

export default function ActionCard() {

    function openWebsite(websiteLink: string) {
      Linking.openURL(websiteLink);
    }

      <TouchableOpacity
          onPress={function(){
              openWebsite('https://www.google.com');
          }}
      >
          <Text>Details</Text>
      </TouchableOpacity>

}
```
6.) TextInput
```javascript
import { Button , Text, TextInput, View } from 'react-native'
import React  from 'react'

export default function App() {
let [name, setName] = useState('')

  return (
      <View>
        <TextInput
        value={sidd}
        style={{borderWidth:1,borderColor:'white'}}
        placeholder='enter name'
        onChangeText={(text)=>{setName(text)}}
        />
        <Button
        title='onPress'
        onPress={()=>setSidd('')}
        />
      </View>
  )
}

secur password attribute
        <TextInput
        secureTextEntry={true}
        onChangeText={(text)=>{setPassword(text)}}
        />
```
7.) FlatList
let userdata = [{ id: 123, name: 'sidd' }]
```javascript
        <FlatList
          data={userData}
          renderItem={({item}) => <Text style={styles.item}>{item.name}</Text>
          keyExtractor={(item) => item.id}
        }
        />
```

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

