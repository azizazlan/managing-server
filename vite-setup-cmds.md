# Setup Vite, Typescript, ESlint and Prettier

## Create vite project

```
npm create vite@latest
```

## Add Eslint

```
npm install -D eslint
```

Then do,

```
npm init @eslint/config
```

select `To check syntax and find problem`

then,

select `JavaScript modules (import/export)`

then,

select `React`

then,

select `Yes` for question "Does your project use Typescript?"

then,

select `Browser` for question "Where does your code run?"

then,

select `Javascript` for question "What format do you want your config file to be in?"

then,

select `Yes` to install the plugins,

## AirBnB

```
npx install-peerdeps --dev eslint-config-airbnb
```

```
npm install eslint-config-airbnb-typescript --save-dev
```

In the `.eslintrc.cjs`, edit as the followings:

```diff
    "extends": [
+       "airbnb",
+       "airbnb-typescript",
        "plugin:react/recommended",
        "plugin:@typescript-eslint/recommended"
    ],

    ...

    "parserOptions": {
        "ecmaVersion": "latest",
        "sourceType": "module",
+       "project" : "./tsconfig.json"
    },

```

In VSCode, press `CMD + SHIP + P`, and type `Reload Window`. Then `ENTER`.

Then, open and edit `tconfig.json`:

```diff
  "include": [
+   ".eslintrc.cjs",
    "src"
  ],
```

## Prettier

```
npm i -D prettier eslint-config-prettier eslint-plugin-prettier
```

Create a `.prettierrc.cjs` in the project root directory.

```
module.exports = {
    trailingComma: "es5",
    tabWidth: 2,
    semi: true,
    singleQuote: true,
  };
```

Edit `.eslintrc.cjs`

```diff
...
  extends: [
    'airbnb',
    'airbnb-typescript',
    'plugin:react/recommended',
    'plugin:@typescript-eslint/recommended',
+   'plugin:prettier/recommended',
  ],

...

plugins: [
    'react',
    '@typescript-eslint',
+   'prettier'
],

...

  rules: {
+   'react/react-in-jsx-scope': 0,
+    'react/jsx-props-no-spreading': 'off',
+    'no-param-reassign': 0,
  },

```

Then VSCode press `CMD + SHIP + P`, then type `Reload Window`.

You can fix by press `CMD + SHIP + P`, then type `ESlint: Fix all auto-fixable Problems`.

## Install dependencies

- react-redux
- react-router-dom
- react-select
- react-hook-form
- @mui/material
- @mui/icons-material
