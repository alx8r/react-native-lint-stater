# Create react-native application

```bash
  npx react-native init {application name} --template react-native-template-typescript
```

# Settup project

```bash
  node -v > .nvmrc
```

```bash
  echo engine-strict=true > .npmrc
```

_Open package.json and past “engines” before “scripts”:_

```
"engines": {
  "node": ">=<your_version>",
  "yarn": ">=<your_version>",
  "npm": "please-use-yarn"
},
```

# Eslint & Prettier

```bash
  echo > .eslintrc & echo > .prettierrc & echo > .prettierignore & echo > .eslintignore
```

```bash
  yarn add -D eslint @typescript-eslint/eslint-plugin @typescript-eslint/parser eslint-config-airbnb eslint-config-airbnb-typescript eslint-plugin-import eslint-plugin-jsx-a11y eslint-plugin-n eslint-plugin-promise eslint-plugin-react eslint-plugin-react-hooks eslint-plugin-react-native prettier
```

**.eslintrc**

```
{
  "env": {
    "browser": true,
    "es2021": true
  },
  "extends": [
    "airbnb",
    "airbnb-typescript",
    "airbnb/hooks",
    "plugin:@typescript-eslint/recommended",
    "plugin:@typescript-eslint/recommended-requiring-type-checking"
  ],
  "overrides": [],
  "parserOptions": {
    "project": "tsconfig.json"
  }
}
```

**.prettierrc**

```
{
  "arrowParens": "always",
  "bracketSameLine": false,
  "bracketSpacing": true,
  "singleQuote": true,
  "quoteProps": "as-needed",
  "semi": true,
  "printWidth": 100,
  "useTabs": false,
  "tabWidth": 2,
  "trailingComma": "es5"
}
```

**.prettierignore & .eslintignore**

```
metro.config.js
__tests__
node_modules/
ios/
android/
vendor/
```

**tsconfig.json**

```
{
  "compilerOptions": {
    "jsx": "react"
  },
  "extends": "@tsconfig/react-native/tsconfig.json",
  "exclude": ["__tests__/**/*-test.ts"]
}
```

_Open package.json and past to “scripts”:_

```
  "lint": "eslint .",
  "prettier": "prettier . --write"
```

# Husky

```bash
  yarn add -D husky
```

```bash
  npx husky install
```

```bash
  npx husky add .husky/pre-commit "yarn lint"
```