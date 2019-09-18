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

# Simpel reload med react-navigation

app.js
```javascript
// In App.js in a new project

import React from 'react';
import { createAppContainer } from 'react-navigation';
import { createStackNavigator } from 'react-navigation-stack';

import WeatherScreen from './screens/WeatherScreen.js'


class Weather extends React.Component {

  render() {
    return (
      <WeatherScreen />
    );
  }
}

const AppNavigator = createStackNavigator({
  Weather: {
    screen: Weather,
  }
});

export default createAppContainer(AppNavigator);

```
screens/WeatherScreen.js
```javascript

import React from 'react';
import { View, Text, Button } from 'react-native';

export default class WeatherScreen extends React.Component {
    state = {
        country: ''
    }

    reload = (country)=>{
        this.setState({country:country})
        this.props.navigation.navigate('Weather', this.state.country)
    }

    render() {
        return (
            <View style={{ flex: 1, alignItems: 'center', justifyContent: 'center' }}>
                <Text>Weather</Text>
                <Text>{this.state.country}</Text>
                <Button
                    title="Denmark"
                    onPress={() => this.reload('Denmark')} />
                <Button
                    title="Sweeden"
                    onPress={() => this.reload('Sweeden')} />
                <Button
                    title="Norge"
                    onPress={() => this.reload('Norge')} />
            </View>
        );
    }
}
```
package.json
```javascript
{
  "main": "node_modules/expo/AppEntry.js",
  "scripts": {
    "start": "expo start",
    "android": "expo start --android",
    "ios": "expo start --ios",
    "web": "expo start --web",
    "eject": "expo eject"
  },
  "dependencies": {
    "expo": "^34.0.1",
    "react": "16.8.3",
    "react-dom": "^16.8.6",
    "react-native": "https://github.com/expo/react-native/archive/sdk-34.0.0.tar.gz",
    "react-native-gesture-handler": "^1.3.0",
    "react-native-web": "^0.11.4",
    "react-navigation": "^4.0.5",
    "react-navigation-stack": "^1.7.3"
  },
  "devDependencies": {
    "babel-preset-expo": "^6.0.0"
  },
  "private": true
}

```
