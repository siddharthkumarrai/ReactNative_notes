# Reat Native Styles

### Styles
#### Inline style
```javascript
<Text style={{fontSize:32}} >hann bhai </Text>
```
#### Internal style
```javascript
import { StyleSheet } from 'react-native'

export default function App() {
  return (
      <Text style={styles.conatiner} >App1</Text>
  )
}

const styles = StyleSheet.create({
  conatiner:{
    fontSize:44
  }
})

```
#### External Style 
> style.tsx
```javascript
import { StyleSheet } from 'react-native'

export default styles = StyleSheet.create({
  conatiner:{
    fontSize:44
  }
})

```
## css property
```
```css
  card: {
    height: 550,
    width: 350,
    borderColor: 'black',
    borderWidth: 0.2,
    borderRadius: 5,
    elevation:0.1
  }
```
