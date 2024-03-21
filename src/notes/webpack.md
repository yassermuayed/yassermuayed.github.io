# Webpack Project Configuration

At its core, webpack is a static module bundler for modern JavaScript applications. When webpack processes your application, it internally builds a dependency graph from one or more entry points and then combines every module your project needs into one or more bundles, which are static assets to serve your content from.

<!-- contents -->
- [Webpack Project Configuration](#webpack-project-configuration)
  - [Packages needed](#packages-needed)
  - [1 Entry And Output](#1-entry-and-output)
  - [2 Setting up HtmlWebpackPlugin](#2-setting-up-htmlwebpackplugin)
  - [3 CSS loader](#3-css-loader)
  - [4 Setting a dev server](#4-setting-a-dev-server)
  - [webpack.config.js final](#webpackconfigjs-final)

## Packages needed

```bash
npm install webpack webpack-cli --save-dev
npm install --save-dev html-webpack-plugin
npm install --save-dev style-loader css-loader
npm install --save-dev webpack-dev-server
```

one liner

```bash
npm install webpack webpack-cli html-webpack-plugin style-loader css-loader webpack-dev-server
```

## 1 Entry And Output

```js
module.exports = {
    entry: './src/main.js',
    output: {
        filename: 'bundle.js',
        path: path.resolve(__dirname, 'dist'),
    },
  };
```

## 2 Setting up HtmlWebpackPlugin

After installing `html-webpack-plugin` We must add to *webpack.config.js* the following:

```javascript
const HtmlWebpackPlugin = require('html-webpack-plugin');
```

And inside *modulee.exports{ }*:

```js
plugins: [
    new HtmlWebpackPlugin({
      title: 'Output Management',
      template: 'src/index.html'
    }),
  ],
```

## 3 CSS loader

```bash
npm install --save-dev style-loader css-loader
```

add a new rule:

```js
module: {
    rules: [
      {
        test: /\.css$/i,
        use: ['style-loader', 'css-loader'],
      },
    ],
  },
```

## 4 Setting a dev server

```bash
npm install --save-dev webpack-dev-server
```

in webpack.config.js add

```js
mode: 'development',
```

and

```js
 devServer: {
    static: './dist',
  },
```

and 

```js
  optimization: {
    runtimeChunk: 'single',
  },
```

and 

```js
output: {
     clean: true,
   },
```

then add

```json
"start": "webpack serve --open",
```

to scripts in `package.json`

## webpack.config.js final

```js
const path = require('path')
const HtmlWebpackPlugin = require('html-webpack-plugin');


module.exports = {
    mode: 'development',
    entry: './src/main.js',
    output: {
        filename: 'bundle.js',
        path: path.resolve(__dirname, 'dist'),
        assetModuleFilename: 'images/[hash][ext][query]',
        clean: true,
    },
    devServer: {
        static: './dist',
    },
    resolve: {
        extensions: ['.ts', '.js'],
    },

    plugins: [
        new HtmlWebpackPlugin({
            title: 'Output Management',
            template: 'src/index.html'
        }),
    ],
    module: {
        rules: [
            {
                test: /\.css$/i,
                use: ['style-loader', 'css-loader'],
            },
            {
                test: /\.(png|svg|jpg|jpeg|gif)$/i,
                type: 'asset/resource',
            },
        ]
    },

};
```
