## Hey there 👋

### Welcome to part two of the setup
> I assume you have the app working on your device.

# Native wind 
It a version of Tailwind css which is a powerful styling sheet
Using it makes code easier and more beautiful

# Set up
create a file called `app.d.ts` in the project files and copy and paste the following
```
/// <reference types="nativewind/types" />
```

You will need to install nativewind and it's peer dependency tailwindcss.
```
yard add nativewind
yarn add --dev tailwindcss@3.3.2
```
Run npx tailwindcss init to create a tailwind.config.js file

Add the paths to all of your component files in your tailwind.config.js file.
```
// tailwind.config.js

module.exports = {
- content: [],
+ content: ["./App.{js,jsx,ts,tsx}", "./screens/**/*.{js,jsx,ts,tsx}"],
  theme: {
    extend: {},
  },
  plugins: [],
}
```
Modify your `babel.config.js`
```
// babel.config.js
module.exports = {
- plugins: [],
+ plugins: ["nativewind/babel"],
};
```

Update the `App.js`
```
import { StatusBar } from 'expo-status-bar';
import React from 'react';
- import { StyleSheet, Text, View } from 'react-native';
+ import { Text, View } from 'react-native';

export default function App() {
  return (
-   <View style={styles.container}>
+   <View className="flex-1 items-center justify-center bg-white">
      <Text>Open up App.js to start working on your app!</Text>
      <StatusBar style="auto" />
    </View>
  );
}

- const styles = StyleSheet.create({
-   container: {
-     flex: 1,
-     backgroundColor: '#fff',
-     alignItems: 'center',
-     justifyContent: 'center',
-   },
- });
```
Thats it 🎉
