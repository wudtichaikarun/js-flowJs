# flowJs

- install and setup environment
- write code and run flow

## install and setup environment

### install

- local

```javascript
npm install --save-dev flow-bin
node_modules/.bin/flow
```

- glgbally

```javascript
npm install -g flow-bin
```

### setup environment

1. install babel-cli and babel-preset-flow

```
yarn add --dev babel-cli babel-preset-flow
```

2. create .babelrc file at the root of your project

```
// .babelrc
{
  "presets": ["flow"]
}
```

3. if you then put all your source in a src directory you can compile them to another directory by running `yarn run babel src/ -- -d lib/`
   You can add this to your package.json scripts

```
// package.json
{
  "name": "my-project",
  "main": "lib/index.js",
  "scripts": {
    "build": "babel src/ -d lib/",
    "prepublish": "yarn run build"
  }
}
```

4. setup flow

- `yarn run flow init` for add .flowconfig file
- `yarn run flow`

## write you code and run flow (add comment // @flow for use flow)

- write code

```javascript
// @flow

function foo(x: ?number): string {
  if (x) {
    return x;
  }
  return 'default string';
}
```

- run flow type `flow` in root project
