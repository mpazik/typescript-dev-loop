# Typescript dev loop
A toolbox package that helps you quickly set up and easily manage your typescript dev loop for your library.

Inspired by [lib-builder](https://github.com/TheUiTeam/lib-builder) and [ts-react-toolbox](https://github.com/zzarcon/ts-react-toolbox).


## What is included
- Typescript
- Jest
- Linter
- Prettier

## Limitations
It does not include any frameworks and it supports only es module.

## Structure
The packet expect that your code will be in the `src` folder.
The build command will generate files in the `dist`.

## Setup
Unfortunately, the setup is a bit more involved than you might expect, as each library does it differently and has its own limitation. Additionally, some dev environments require config files to be set up in the project's root directory.

If you know how the set-up process could be improved, please open an issue or pull a request. All ideas and contributions are welcome!

### 1. Install
Install as dependency

`npm install typescript-dev-loop --save-dev`

or 

`yarn add -D typescript-dev-loop`

### 2. Typescript
Create `tsconfig.json` file

```json
{
  "extends": "./node_modules/typescript-dev-loop/config/tsconfig.json",
  "include": [
    "src"
  ],
  "exclude": [
    "dist",
    "node_modules",
    "src/**/*.test.ts"
  ]
}
```

### 3. Lint
Add to `package.json` file

```json
{
  "eslintConfig": {
    "root": true,
    "extends": "./node_modules/typescript-dev-loop/config/eslint.json"
  }
}
```

### 4. Jest
Create `jest.config.js` file

```js
import jest from "typescript-dev-loop/jest";
export default jest;

```

### 5. Run scripts
Add to `package.json` file

```json
{
  "scripts": {
    "build": "tdl-build",
    "prepack": "yarn build",
    "lint": "tdl-lint",
    "test": "tdl-test"
  }
}
```

## License
[The MIT License](./LICENSE) © Marek Pazik
