# How to add NativeWind in a typescript react native project?

## Requirements

- A react native project
- Tailwind CSS IntelliSense (extension)
- Yarn

## Step-by-step

### 1. Add dependencies

- Add nativewind

```shell
yarn add nativewind
```

- Add tailwindcss as a development dependency.

```shell
yarn add --dev tailwindcss
```

### 2. Setup Tailwind CSS

- Create a tailwind config file

```shell
yarn tailwindcss init
```

- Change the tailwind config file (**tailwind.config.js**)

```javascript
/** @type {import('tailwindcss').Config} */
module.exports = {
  content: ["./App.{ts,tsx}", "./src/**/*.{ts,tsx}"],
  theme: {
    extend: {},
  },
  plugins: [],
};
```

### 3. Add the Babel plugin

- Add a plugin on Babel config file (**babel.config.js**)

```javascript
module.exports = function (api) {
  api.cache(true);
  return {
    presets: ["babel-preset-expo"],
    plugins: ["nativewind/babel"],
  };
};
```

### 4. Add a config file for TypeScript support

- Create ot update a config file (**app.d.ts**) at your source code folder like (**./src/types**)

> This config file should not be called as nativewind.d.ts

```javascript
<reference types="nativewind/types" />
```

## Troubleshooting

### Android Bundling Failing

> Android Bundling failed 2941ms
> error: App.tsx: D:\Codes\ReactNative\navigation-tailwind\App.tsx: Use process(css).then(cb) to work with async plugins

- Try install this specific version

```shell
yarn add --dev tailwindcss@3.3.2
```
