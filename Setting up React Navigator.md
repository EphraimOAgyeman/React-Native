# Hey
Navigator as the name suggest is for all page navigations in the app and is very important.

1. Install the required packages in your React Native project:
   ```
   npm install @react-navigation/native
   ```
2. In your project directory, run:
   ```
   npx expo install react-native-screens react-native-safe-area-context
   ```

3. Now, we need to wrap the whole app in `NavigationContainer`. Usually you'd do this in your entry file, `App.js`
   ```
   import * as React from 'react';
   import { NavigationContainer } from '@react-navigation/native';

   export default function App() {
     return (
        <NavigationContainer>{/* Rest of your app code */}</NavigationContainer>
      );
     }
   ```
4. To use the native stack navigator, we need to install
   ```
   npm install @react-navigation/native-stack
   ```

5. Update the App.js to this
   ```
   // In App.js in a new project

   import * as React from 'react';
   import { View, Text } from 'react-native';
   import { NavigationContainer } from '@react-navigation/native';
   import { createNativeStackNavigator } from '@react-navigation/native-stack';

   function HomeScreen() {
     return (
       <View style={{ flex: 1, alignItems: 'center', justifyContent: 'center' }}>
         <Text>Home Screen</Text>
       </View>
     );
   }

   const Stack = createNativeStackNavigator();

   function App() {
     return (
       <NavigationContainer>
         <Stack.Navigator>
           <Stack.Screen name="Home" component={HomeScreen} />
         </Stack.Navigator>
       </NavigationContainer>
     );
   }

   export default App;
   ```
6. Create a folder called `screens`, in it create a file called `HomeScreen`
7. Open it and type `rnfe` after installing the extension `ES7+React/...`
