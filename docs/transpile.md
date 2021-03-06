# Transpile

The compilation target of this library and related dependencies is [defaults browserlist](https://browserl.ist/?q=defaults), covering 90% of browsers. If you need to be compatible with more browsers, you need to add related dependencies to the transpile list. The following solution also applies to other third-party dependencies.

<del>This library and related dependencies provide es6, commonjs, umd build results. vue-cli and Nuxt use es6 files by default. But their babel config do not compile third-party dependencies by default, so the compiled result will include es6 syntax, which will cause syntax errors in older browsers, such as ie11. Follow is the solution.</del>

## vue-cli
Add related dependencies in `transpileDependencies` of `vue.config.js`.
```js
module.exports = {
  TranspileDependencies: ['he-tree-vue', 'helper-js', 'draggable-helper', 'vue-functions', 'drag-event-service'],
}
```

## nuxt
Add related dependencies in `build.transpile` of `nuxt.config.js`.
```js
module.exports = {
  build: {
    transpile: ['he-tree-vue', 'helper-js', 'draggable-helper', 'vue-functions', 'drag-event-service'],
  }
}
```