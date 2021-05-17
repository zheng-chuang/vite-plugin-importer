# vite-plugin-importer

Integration for babel-plugin-import

## use

config same as [babel-plugin-import](https://github.com/ant-design/babel-plugin-import)

```
npm install vite-plugin-importer --save
yarn add vite-plugin-importer
```

```js
// vite.config.js
import { defineConfig } from "vite";
import usePluginImport from 'vite-plugin-importer'
export default defineConfig({
  plugins: [
    ... // other plugins
    usePluginImport({
      libraryName: "ant-design-vue",
      libraryDirectory: "es",
      style: "css",
    }),
    usePluginImport({
      libraryName: "antd",
      libraryDirectory: "es",
      style: "css",
    }),
    usePluginImport({
      libraryName: 'vant',
      libraryDirectory: 'es',
      style: (name) => `${name}/style/less`,
    }),
    usePluginImport({
      libraryName: "element-plus",
      libraryDirectory: "es",
      customStyleName: (name) => {
        if (name === 'locale') {
          return `element-plus/packages/theme-chalk/src/button.scss`
        }
        return `element-plus/packages/theme-chalk/src/${name.replace('el-','')}.scss`;
      },
    }),
  ];
})

```

## LICENSE

[MIT](./LICENSE)
