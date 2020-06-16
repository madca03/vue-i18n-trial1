# vue-i18n-test1

## Project setup
1. To use vue-i18n, you need to install the following as development dependencies: vue-loader & vue-i18n-loader. See this [link][install] for more information.
  ```
  npm install --save-dev vue-loader @kazupon/vue-i18n-loader
  ```
  
2. To add support for **\<i18n\>** tag inside single file components, we need to modify some webpack configuration. To do this, create a file named **vue.config.js** in the root of your directory and add the code below.
  ```
  module.exports = {
    chainWebpack: config => {
      config.module
        .rule("i18n")
        .resourceQuery(/blockType=i18n/)
        .type('javascript/auto')
        .use("i18n")
          .loader("@kazupon/vue-i18n-loader")
          .end();
    }
  }
  ```

### Compiles and hot-reloads for development
```
npm run serve
```

### Compiles and minifies for production
```
npm run build
```

### Lints and fixes files
```
npm run lint
```

### Customize configuration
See [Configuration Reference](https://cli.vuejs.org/config/).

[install]: https://kazupon.github.io/vue-i18n/guide/sfc.html#installing-vue-i18n-loader
