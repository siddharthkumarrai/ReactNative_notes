# ReactNative_notes
### install react-native new project
```javascript
npx react-native init basicreactnative
```
```javascript
npx @react-native-community/cli init backgroundchanger03
```
>android/local.properties
```javascript
sdk.dir=C:\\Users\\siddh\\AppData\\Local\\Android\\Sdk
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
7.) StatusBar
```javascript
<StatusBar backgroundColor="black" />
```
8.) Pressable
```javascript
      <Pressable onPress={function}>
        <Text>press</Text>
      </Pressable>
```
9.) FlatList
```javascript
let userdata = [{ id: 123, name: 'sidd' }]
        <FlatList
          data={userData}
          renderItem={({item}) => <Text style={styles.item}>{item.name}</Text>
          keyExtractor={(item) => item.id}
        }
        />
```

10.) SectionList

```javascript
import React,{useState} from "react";
let [name,setName] = useState("sidd")

const DATA = [
  {
    title: 'Main dishes',
    data: ['Pizza', 'Burger', 'Risotto'],
  },
];

    <SectionList
      sections={DATA}
      keyExtractor={(item, index) => item + index}
      renderItem={({item}) => (
        <View style={styles.item}>
          <Text style={styles.title}>{item}</Text>
        </View>
      )}
      renderSectionHeader={({section: {title}}) => (
        <Text style={styles.header}>{title}</Text>
      )}
    />
```
11.) ImageBackground
```javascript
import {ImageBackground, StyleSheet, Text} from 'react-native';

<ImageBackground source={image} resizeMode="cover" style={styles.image}>
        <Text style={styles.text}>Inside</Text>
</ImageBackground>
```
- source={require('../../assets/image.png')}

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
## How to handle Image in React-Native
-  step 1: make ```assets``` folder in root directory
> assets
```javascript
one.png
```
-  step 2: import images
```javascript
import DiceOne from '../assets/One.png'
```
- step 3: make file ```index.d.ts``` in src directory
>index.d.ts
```javascript
declare module '.*png'
```
- step 4: declare type ImageSourcePropType
```javascript
import { ImageSourcePropType } from 'react-native'
import React, { PropsWithChildren } from 'react'

type diceProperty = PropsWithChildren<{
  imageUrl: ImageSourcePropType
}>
```
- step 5: making a ImageName component
```javascript
let HandleDiceImage = ({imageUrl}:diceProperty):JSX.Element =>{
  return(
    <View>
      <Image style={{height:100, width: 100}} source={imageUrl}/>
    </View>
  )
}
```
- step 6: use the imageName component
```javascript
export default function App():JSX.Element {
const [dice, setDice] = useState < ImageSourcePropType>(DiceOne);
  return (
      <HandleDiceImage imageUrl={dice} />
  )
}
```

## dependencies
1.) yup (Form validation)
```javascript
npm i yup
```
```javascript
import * as Yup from 'yup'

const passwordSchema = Yup.object().shape({
  passwordLength: Yup.number()
  .min(4,'should be min of 4 characters')
  .max(16,'should be max of 16 characters')
  .required('length is required')
})
```
2.) Formik (for form handling)
```javascript
npm i formik
```
```javascript
import {Formik} from 'formik';
<Formik
            initialValues={{passwordLength: ''}}
            validationSchema={passwordSchema}
            onSubmit={value =>
              createPasswordString(Number(value.passwordLength))
            }>
            {({
              values,
              errors,
              touched,
              handleChange,
              handleSubmit,
              handleReset,
              isValid,
            }) => (
              <>
                    {touched.passwordLength && errors.passwordLength && (
                      <>
                          {errors.passwordLength}
                      </>
                    )}
                  <TextInput
                    value={values.passwordLength}
                    onChangeText={handleChange('passwordLength')}
                    placeholder="Ex. 8"
                    keyboardType="numeric"
                  />
                  <TouchableOpacity
                    style={styles.secondaryBtn}
                    disabled={!isValid}
                    onPress={() => {
                      resetPassword();
                      handleReset();
                    }}>
                  </TouchableOpacity>
              </>
            )}
</Formik>
```
3.) react-native-bouncy-checkbox
```javascript
npm i react-native-bouncy-checkbox
```
```javascript
import BouncyCheckbox from 'react-native-bouncy-checkbox';

    <Text style={styles.heading}>Include SpecialCharacter</Text>
    <BouncyCheckbox
      disableText
      isChecked={specialCharacter}
      fillColor="#e0aaff"
      onPress={() => setSpecialCharacter(!specialCharacter)}
    />
```
4.) react-native-haptic-feedback

[Read docs](https://www.npmjs.com/package/react-native-haptic-feedback)

5.) react-native-snackbar

## PROJECT
> src/screens/splash
```javascript
import { View, Text, ImageBackground } from 'react-native';

export default function SplashScreen() {
    return (
        <ImageBackground
            source={require('../../../assets/splashscreenbackgroundimage.png')}
            style={{ flex: 1 }}
            resizeMode={'stretch'}
        >
                <Text>
                    Welcome
                </Text>
        </ImageBackground>
    );
}
```
### Navigation
- Installation
```javascript 
npm install @react-navigation/native
```
```javascript 
npm install react-native-screens react-native-safe-area-context
```
- react-native-screens package requires one additional configuration
> android/app/src/main/java/<your package name>/ MainActivity.kt
-  import statement at the top of this file below your package statement:
```javascript
import android.os.Bundle;
```
```javascript
class MainActivity: ReactActivity() {
  // ...
  override fun onCreate(savedInstanceState: Bundle?) {
    super.onCreate(null)
  }
  // ...
}
```
- Installing the native stack navigator library
```javascript
npm install @react-navigation/native-stack
```
> App.jsx
```javascript
import React from 'react';
import SplashScreen from './src/screens/splash';
import {NavigationContainer} from '@react-navigation/native';
import {createNativeStackNavigator} from '@react-navigation/native-stack';

const Stack = createNativeStackNavigator();
function App() {
  return (
    <NavigationContainer>
      <Stack.Navigator>
        <Stack.Screen
          name="home"
          component={SplashScreen}
          options={{headerShown: false}}
        />
      </Stack.Navigator>
    </NavigationContainer>
  );
}

export default App;
```
