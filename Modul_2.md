# Modul 2
### Indhold
Vi skal se på layout og arbejde med data fra interne og eksterne kilder

## Style og Flexbox
http://www.reactnativeexpress.com/flexbox

https://medium.com/wix-engineering/the-full-react-native-layout-cheat-sheet-a4147802405c

## Forøvelse - Udskriv data fra et array
Du får her et lille array med objekter, som du skal udskrive i din app.
`Vi ser på det sammmen bagefter`
```javascript
    andeby = [
        { id: 1, name: 'Anders And' },
        { id: 2, name: 'Mickey Mouse' },
        { id: 3, name: 'Fedtmule' }
    ]
```

En løsning...
```javascript
import React, { Component } from 'react'
import { Text, StyleSheet, View } from 'react-native'

export default class ArrayList extends Component {

    andeby = [
        { id: 1, name: 'Anders And' },
        { id: 2, name: 'Mickey Mouse' },
        { id: 3, name: 'Fedtmule' }
    ]

    renderContent() {
        return this.andeby.map((item) => {
            return (
                <Text key={item.id} style={styles.content}>
                    {item.name}
                </Text>
            );
        });
    }

    render() {
        return (
            <View>
                {this.renderContent()}
            </View>
        )
    }
}

const styles = StyleSheet.create({
    content: {
        backgroundColor: 'orange',
        margin: 2,
        width: 200,
        textAlign: "center", fontSize: 20
    }
})
```

jo, der kommer mere :)

### Flatlist
http://www.reactnativeexpress.com/flatlist

### Sectionlist
http://www.reactnativeexpress.com/sectionlist

https://facebook.github.io/react-native/docs/flatlist

