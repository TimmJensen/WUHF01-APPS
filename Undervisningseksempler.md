# Eksempler fra undervisingen

## Forøvelse - Udskriv data fra et array

https://reactjs.org/docs/lists-and-keys.html#keys

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
