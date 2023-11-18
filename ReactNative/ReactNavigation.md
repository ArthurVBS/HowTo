# How to add ReactNavigation in a typescript react native project?

## Requirements

- A react native project
- Npx
- Yarn

## Step-by-step

### 1. Add core dependencies

- Add react navigation core dependency

```shell
yarn add @react-navigation/native
```

- Add others react navigation core dependencies

```shell
npx expo install react-native-screens react-native-safe-area-context
```

### 2. Add a navigation you will work with

#### 2.1. Stack Navigation

- Add stack navigation dependency

```shell
yarn add @react-navigation/native-stack
```

#### 2.2. Tab Navigation

- Add tab navigation dependency

```shell
yarn add @react-navigation/bottom-tabs
```

#### 2.3. Drawer Navigation

- Add drawer navigation dependency

```shell
yarn add @react-navigation/drawer
```

- Add others drawer navigation dependencies

```shell
npx expo install react-native-gesture-handler react-native-reanimated
```

- Add react native gesture handler at your main file like (**App.tsx**)

```javascript
import "react-native-gesture-handler";
```

- Add a plugin on Babel config file (**babel.config.js**)

```javascript
module.exports = function (api) {
  api.cache(true);
  return {
    presets: ["babel-preset-expo"],
    plugins: ["react-native-reanimated/plugin"],
  };
};
```

### 3. Using a navigation

- Create a route file like (**./src/routes/tab.routes.tsx**)

- Config your route file

> In this case I'm using the Tab Navigator

```javascript
import { createBottomTabNavigator } from "@react-navigation/bottom-tabs";

import Component1 from "../screens/Component1";
import Component2 from "../screens/Component2";

const Tab = createBottomTabNavigator();

export default function TabRoutes() {
  return (
    <Tab.Navigator>
      <Tab.Screen name="Component1" component={Component1} />
      <Tab.Screen name="Component2" component={Component2} />
    </Tab.Navigator>
  );
}
```

- Create a index route file like (**./src/routes/index.tsx**) to encapsulate the routes navigation

- Config your index route file

```javascript
import { NavigationContainer } from "@react-navigation/native";
import TabRoutes from "./tab.routes";

export default function Routes() {
  return (
    <NavigationContainer>
      <TabRoutes />
    </NavigationContainer>
  );
}
```

- Add your routes at the initial file like (**App.tsx**)

```javascript
import Routes from "./src/routes";

export default function App() {
  return <Routes />;
}
```

## Troubleshooting

### Dependency version error

> Error: [Reanimated] Mismatch between JavaScript part and native part of Reanimated (3.5.4 vs 3.3.0).

- Try to update and fix all dependencies versions

```shell
npx expo install --fix
```
