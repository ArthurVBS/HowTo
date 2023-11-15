# How to create a react native project with typescript, eslint, prettier?

## Requirements

- ESLint (extension)
- Expo
- NodeJS
- Prettier (extension)
- Yarn

## Step-by-step

### 1. Create an expo app

- Create an expo app with a template.

```shell
yarn create expo my-app-name --template
```

- Choose a template.

> - Blank(TypeScript)

- Then enter on directory.

```shell
cd my-app-name
```

### 2. Add ESLint

- Add ESLint as a development dependency.

```shell
yarn add eslint -D
```

### 3. Config ESLint

- Init ESLint config.

```shell
yarn eslint --init
```

> My Configuration is:
>
> - To check syntax, find problems, and enforce code style
> - JavaScript modules (import/export)
> - React
> - Yes
> - Node & Browser
> - Answer questions about your style
>   > - Json
>   > - Spaces
>   > - Single
>   > - Unix
>   > - Yes
> - Yes
> - Yarn

#### My .eslintrc file

```javascript
{
  "env": {
    "browser": true,
    "es2021": true,
    "node": true
  },
  "extends": [
    "eslint:recommended",
    "plugin:@typescript-eslint/recommended",
    "plugin:react/recommended",
    "plugin:react/jsx-runtime"
  ],
  "parser": "@typescript-eslint/parser",
  "parserOptions": {
    "ecmaVersion": "latest",
    "sourceType": "module"
  },
  "plugins": ["@typescript-eslint", "react"],
  "rules": {
    "indent": ["error", 2],
    "linebreak-style": ["error", "unix"],
    "quotes": ["error", "single"],
    "semi": ["error", "always"]
  }
}
```

### 4. Add prettier

- Create a file called **.prettierrc**.

- Then add your configuration.

#### My .prettierrc file

```javascript
{
  "trailingComma": "none",
  "semi": true,
  "singleQuote": true,
  "endOfLine": "lf",
  "tabWidth": 2,
  "useTabs": false,
  "arrowParens": "avoid",
  "printWidth": 80
}
```
