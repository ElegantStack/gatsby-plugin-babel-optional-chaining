# Gatsby plugin for babel optional chaining operator

## Description

This plugin enables the optional chaining operator (`a?.b`) [TC39 proposal](https://github.com/tc39/proposal-optional-chaining) for Gatsby.

## How to install

Install the plugin and its dependencies:

```bash
npm i gatsby-plugin-babel-optional-chaining @babel/core @babel/plugin-proposal-optional-chaining
```

or

```bash
yarn add gatsby-plugin-babel-optional-chaining @babel/core @babel/plugin-proposal-optional-chaining
```

Add the plugin to `gatsby-config.js`:

```js
module.exports = {
  plugins: [
    // other plugins
    'gatsby-plugin-babel-optional-chaining',
  ],
}
```

## Examples of usage

```js
const obj = {
  foo: {
    bar: {
      baz: 42,
    },
  },
};

const baz = obj?.foo?.bar?.baz; // 42

const safe = obj?.qux?.baz; // undefined

// Optional chaining and normal chaining can be intermixed
obj?.foo.bar?.baz; // Only access `foo` if `obj` exists, and `baz` if
                   // `bar` exists

// Example usage with bracket notation:
obj?.['foo']?.bar?.baz // 42
```
