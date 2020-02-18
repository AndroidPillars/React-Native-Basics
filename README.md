# React-Native Basics

# React Native

- It is an amazing technology that allows you to build real native apps which you can ship to the Apple App Store and the 
Google Play Store with the help of Javacript and React library.

# React.js

- It is a javascript library for building user interfaces.
- Typically used for Web Development.
- ReactDOM.render(...) adds the web support.
- React itself is Platform agnostic.

# React Native

- It is a seperate library which in the end is a collection of special React components it gives you, so a collection of components you can use in your React app and these components are special because React Native  actually knows how to translate them, how to compile these components to native widgets for ios and Android. So React Native kind of is like React DOM, it knows how to talk to native platform, to Android and iOS and how to render native widgets and it gives a bunch of these widgets as React components so that you can build a user interface with these compilable components(i.e)you won't be able to use your regular divs and h1 and paragraph tags in React Native because there are no equivalents for that in Native Code. But beside giving you this components, React Native is a bit more than that, it also gives access to some native platform APIs, For example it helps us to use the device camera, common tasks you would want to do in Native Apps and in general React Native gives you to tools to connect javascript code to native platform code because
you typically build a React Native app by mostly writting Javascript code or depending on the app you're building, by entirely writing Javascript. 


# Installation

For Windows,

- Visit			-> https://expo.io/learn
- Install Node		-> https://nodejs.org/en/download/
- Cmd Prompt		-> npm install expo-cli --global
- Required Folder 	-> Open Cmd Prompt -> expo init my-new-project name -> Choose a template: expo-template-blank
- Project path		-> Cmd Prompt -> npm start
- In Mobile Device	-> Download Expo app from playstore -> Scan the QR Code
- ctrl+c			-> Close

# Reference Website

- https://expo.io/learn
- https://facebook.github.io/react-native/docs/getting-started
- https://git-scm.com/
- https://www.yelp.com/fusion

# Commands to get Remember

```ruby
expo start		-> Start the Project
expo start --android	-> Start the Project in Android
```


# Common Errors

- warn Package react-native-gesture-handler has been ignored because it contains invalid configuration. Cannot find module 'react-native-gesture-handler\package.json',
```ruby
npm uninstall react-native-gesture-handler --save
npm install react-native-gesture-handler --save
```
- npm ERR! code ENOENT npm ERR! syscall spawn git npm ERR! path git,

Have to Install the Git

- Found 15 vulnerabilities
```ruby
npm audit fix --force
```
- For adding Navigation,

```ruby
expo install react-navigation react-native-gesture-handler@1.3.0 react-native-reanimated react-native-screens react-navigation-stack react-native-safe-area-context @react-native-community/masked-view
```

# React Component File

- Part 1 -> Import library we need to create component

```ruby
import React from "react";
import { Text, StyleSheet } from "react-native";
```
- Part 2 -> Create a component - function that returns some 'JSX'

```ruby
Normal Function:

const HomeScreen = function() {
  return <Text style={styles.text}>HelloWorld!!!</Text>;
};

Arrow Function:

const HomeScreen = () => {
  return <Text style={styles.text}>HelloWorld!!!</Text>; 
};

Inline Style:

const HomeScreen = () => {
  return <Text style={{fontSize: 30}}>HelloWorld!!!</Text>;  
};


Note: Semicolon is not necessary.
```

- Part 3 -> Create a Style sheet to create our component.

```ruby
const styles = StyleSheet.create({
  text: {
    fontSize: 30 
  } 
});
```

- Part 4 -> Export the Component so that we caan use it else where in our project.
```ruby
export default HomeScreen;
```

# Showing Custom Component

- Open App.js 
- import ComponentScreen from "./src/screens/ComponentScreen";
```ruby
  const navigator = createStackNavigator(
  {
    Home: HomeScreen,
    Components: ComponentScreen 
  },
  {
    initialRouteName: "Components",
    defaultNavigationOptions: {
      title: "App"
    }
  }
);
```
# Common Questions and Answers

- Primitive Elements -> Text, View, Image and Button,.. etc..
- 'JSX' -> <Text style={styles.text}>HelloWorld!!!</Text> -> It passes in to the react native bundler that one is using a 
  tool called babel to convert that in to javascript code.

- Reference: https://babeljs.io/

- createStackNavigator -> It is a tool Which is used to navigates from one screen to another screen.
- StyleSheet.create -> To Style the primitive elements.

# Rules of JSX

- If we place a Text inside a View, we should remove the semicolon of Text widget.
- We can declare a string global and re-use that as, const mTxtHello = 'Hi, How are you?' -> <Text>{mTxtHello}</Text> similary for         array, boolean and int.
- Similarly,  const mTxtHello = <Text>'Hi, How are you?'</Text> -> {mTxtHello}

# Common Errors

```ruby
return (
    <View>
    <Text style={styles.text}>HelloWorld!!!</Text>
    {mTxtHello}
    </View>
    );
```
 or
```ruby
return <View>
    <Text style={styles.text}>HelloWorld!!!</Text>
    {mTxtHello}
    </View>
```
# BoilerPlate Code

```ruby
import React from "react";
import { Text, StyleSheet, View } from "react-native";

const ListScreen = ()=>{
return<Text>List Screen</Text>
}

const styles = StyleSheet.create({});

export default ListScreen;
```
# Building List

- primitive Element -> FlatList Element
- It take in a array of records and turn it in to some list and display
- Props -> Props are configuration options we specify when we write it out a JSX element.
- Two Props 
- 1. Data -> Array of data  so that it will turn in to a collection of elements to show on the Screen.
- 2. RenderItem -> Function that will turn each individual item in to an Element.
- Note: Behaviour with out a key being provided gives warning. 
- For that we have to assign a key which it must be a string and also it should be unique.

# Button

- It has self closing Tag

# Touchable Opacity(i.e) Customizable Component

- Alternative widgets to Button

# Props

- It has lot of properties which we can navigate from one screen to another From React Naivgation Stack 
Navigator to Required Screens. 
- In Other words system to pass data from a parent to child.
- Work Flow: React Naivgation Stack Navigator -> props -> Navigator to Required Screens 

# State

- System to track a piece of data that will change over time. If that data changes, our app will 'rerender'.

# Notes on State

- We are using function-based state in a functional component. React also has class based components that have to access state.
- We never modify a state variable . React doesn't detect the change, Only use the 'setter' function.
- We can name the state variable anything we wish.
- We can track any kind of data that changes over time - a number, string, array of objects, ect
- When a component is rendered, all of its children get renendered to.
- A state variable can be passed to a child component ! At that time, the state variable is being used as props.

# Layout Systems

# Box Object Model

- Properties like Border, Margin, Padding and the Width and Height of some element. We
use this to affect the positioning of single element.
- Content -> Padding -> Border -> Margin
- Height  -> paddingTop -> borderTopWidth -> marginTop
- For Parent -> alignItems, justifyContent and flexDirection
- Short Cuts -> margin, marginVertical, marginHorizontal, padding, paddingVertical, paddingHorizontal and borderWidth

# Flex Box

- The Flex Box system is considered from how we layout some number of child elements that has own number of common parent. We use this to position mulitple elements with a common parent. 
- For Child  -> flex, alignSelf

# Position

- How to position a element inside of a child. One single child inside of a parent. We use 
this to override Box object model + Flex Box

# Layout  Systems

- Apply box object model Class -> Is position 'absolute'
- No -> Apply all flex box rules, Considering siblings -> place element inside parent -> Apply top, left, right and bottom
- Yes -> Apply some flex box rules, ignore all siblings -> Apply top, left, right and bottom.

# Parent Properties

- alignItems -> Similar to MatchParent and WrapContent.
- JustifyContent -> similar to that of setting gravity.
- flexDirection -> Indicates horizontal and Vertical position.

# Child Properties

- flex -> Similar to that of weight .
- alignself -> Similar to that of MatchParent and WrapContent also think that of parent right(i.e)It override the parent element.

# Position Properties

- position -> Similar to that of Frame Layout, Relative Layout and Linear Layout.
- top,bottom,left and Right -> Similar to that of margin.

# expo-cli

- Adds in a ton of default config to use features common in apps, like icons, videos, better camera use, etc

# react-native-cli

- Defualt CLI to generate a project. Requires a lot of work to add in common Features.

# Documentation for the Search API

- https://www.yelp.com/fusion
- Create the account using VPN
- Get Started -> Create New App -> Save Client ID and API Key
- Menu -> Business Endpoints -> Business Search, Business Details

# React Navigation Library

- React Navigation Library provides us a couple of different objects for navigating users around an App.
- In particular three important objects -> Stack Navigator, Bottom Tab Navigator and Drawer Navigator.

# React Navigation Fix

- React Navigation has recently released a major update to v5 with breaking changes. We will not be using this version and will instead continue to use the current stable v4 release (As of now at v4.1.1)

1. Install React Navigation
```ruby
npm install react-navigation
```
2. Install Dependencies
```ruby
expo install react-native-gesture-handler react-native-reanimated react-native-screens react-native-safe-area-context @react-native-community/masked-view
```
3. Install React Navigation Stack
```ruby
npm install react-navigation-stack @react-native-community/masked-view
```
4. Start the app and clear cache with 
```ruby
npm start -c
```

# Still Errors?

- If you are still seeing errors and complaints about packages, do the following:
```ruby
rm -r node_modules
rm package-lock.json
expo upgrade
npm start -c
```

# Update Imports

- Our imports in the upcoming lecture will now look like this:
```ruby
import { createAppContainer } from 'react-navigation';
import { createStackNavigator } from 'react-navigation-stack';
```
# Icon Listing

- https://github.com/expo/vector-icons

# Network Request

- The two things used for to make a network request in ReactNative is fetch and axios

# fetch 

- Built in Function for making network request.
- Error handling is a bit weird.
- Requires us to write a lot of wrapper code to make it work 'sensibly'.

# axios

- Seperate library for making request.
- Easy to use, Sensible defaults.
- Little bit increase our App size.
- In Project Folder -> Open cmd prompt npm install axios

# Hook

- Hook is a function that adds in some new type of functionality to the function component.

# useEffect 

- It is a Hook or essentially a function that allows us to run some snippet of code, one time 
when ever the component is first rendered to the screen.

# useState's Second Argument

```ruby
useState(() => {})
```
- Run the arrow function every time the component is rendered.
```ruby
useState(() => {}, [])
```
- Run the arrow function only when the component is first rendered.
```ruby
useState(() => {}, [value])
```
- Run the arrow function only when the component is first rendered, and when the 'value' changes.

# Reducers

- Functions that manages changes to an object.
- Arguement #1 -> Object that has all of our state in it. -> {red:0, green:0, blue:0}
- Arguement #2 -> Object that describes the update that we want to make.->{colorToChange:'red', amount: 15}
- We look at Arguement #2 and use it to decide how to change Arguement #1.
- Two technicalities - (1) We never change Arguement #1 directly, (2) We must always return a value to be used as Arguement #1

# Community Convention in Reducers

- Our Action Object Head,
```ruby
{ colorToChange: 'red', amount: 15 }
```
Usually, by Convention, we'll use instead,
```ruby
{ type:'change_red', payload: 15 }
```
where, 
type -> String that dessribes that extact change operation we want to make.
payload -> Some data that is critical to the change Operation.

