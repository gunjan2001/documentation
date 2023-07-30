# Webpack:

- It’s a very popular and powerful tool for configuring not only React, but almost all front-end projects.
- The core function of webpack is that it takes a bunch of JavaScript files we write in our project and turns them into a single, minified file, so that it will be quick to serve.

## Webpack Setup Guid:

**1. Open up the command line or Git bash and create a new directory:**

```
mkdir your-folder-name && cd your-folder-name
```

**2. Initialize NPM project by running:**

```
npm init -y
```

**3. Create your src folder and add files:**

- like index.html, App.jsx or index.jsx

**4. Install the `react` and `reactDOM`:**

```
npm install react react-dom
```

**5. Configuring webpack :**

```
npm install -D webpack webpack-dev-server webpack-cli html-webpack-plugin webpack-merge @pmmmwh/react-refresh-webpack-plugin
```

- -D means dev dependency.
- `webpack module` — which include all core webpack functionality
- `webpack-dev-server` — this development server automatically rerun webpack when our file is changed
- `webpack-cli` — enable running webpack from the command line
- `webpack-merge` : for merge common webpack file with prod and dev files.
- `@pmmmwh/react-refresh-webpack-plugin`: A Webpack plugin to enable "Fast Refresh" (also previously known as Hot Reloading) for React components.

**6. Install babel and babel-loader:**

```
npm install -D @babel/core @babel/preset-env @babel/preset-react @babel/plugin-transform-runtime @babel/runtime babel-loader

```

**Usages:**

- `@babel/core`: It is the main dependency that includes babel transform script.
- `@babel/preset-env`: It is the default Babel preset used to transform ES6+ into valid ES5 code. Optionally configures browser polyfills automatically.
- `@babel/preset-react`: It is used for transforming JSX and React class syntax into valid JavaScript code.
- `babel-loader`: It is a webpack loader that hooks Babel into webpack. We will run Babel from webpack with this package.
- `@babel/plugin-transform-runtime` : Purpose of this transformer is to create a sandboxed environment(is an environment in which unsafe software code can execute without affecting network resources or local applications.) for your code.
- `@babel/runtime`: A library that contains Babel modular runtime helpers.

7. Create a webpack folder and create webpack.common.js, webpack.config.js, webpack.dev.js, webpack.prod.js.

- In common.js take path using reqiure("path") and html plugin.

**Format:**

**common.js**

```
const path = require("path");
const HtmlWebpackPlugin = require("html-webpack-plugin");

module.exports = {
  entry: path.resolve(__dirname, "..", "./src/index.js"),
  resolve: {
    extensions: [".js"],
  },
  module: {
    rules: [
      {
        test: /\.(js|ts)x?$/,
        exclude: /node_modules/,
        use: [
          {
            loader: "babel-loader",
          },
        ],
      },
      {
        test: /\.css$/,
        use: ["style-loader", "css-loader"],
      },
      {
        test: /\.(?:ico|gif|png|jpg|jpeg)$/i,
        type: "asset/resource",
      },
      {
        test: /\.(woff(2)?|eot|ttf|otf|svg|)$/,
        type: "asset/inline",
      },
    ],
  },
  output: {
    path: path.resolve(__dirname, "..", "./build"),
    filename: "bundle.js",
  },
  plugins: [
    new HtmlWebpackPlugin({
      template: path.resolve(__dirname, "..", "./src/index.html"),
    }),
  ],
  stats: "errors-only",
};

```

**dev.js**

```
const ReactRefreshWebpackPlugin = require("@pmmmwh/react-refresh-webpack-plugin");

module.exports = {
  mode: "development",
  devtool: "cheap-module-source-map",
  devServer: {
    hot: true,
    open: true,
  },
  plugins: [new ReactRefreshWebpackPlugin()],
};

```

**prod.js**

```
module.exports = {
  mode: "production",
  devtool: "source-map",
};

```

**config.js**

```
const { merge } = require("webpack-merge");
const commonConfig = require("./webpack.common.js");

module.exports = (envVars) => {
  const { env } = envVars;
  const envConfig = require(`./webpack.${env}.js`);
  const config = merge(commonConfig, envConfig);
  return config;
};

```

**8. Create .babelrc file:**

```
{
  "presets": [
    "@babel/preset-env",
    [
      "@babel/preset-react",
      {
        "runtime": "automatic"
      }
    ]
  ],
  "plugins": [
    [
      "@babel/plugin-transform-runtime",
      {
        "regenerator": true
      }
    ]
  ]
}
```

**9. Update packet.json:**

- Add below snippest in `script`:

```
    "start": "webpack serve --config webpack/webpack.config.js --env env=dev",
    "build": "webpack --config webpack/webpack.config.js --env env=prod"
```

**10. Adding style loader**

- Run below command:

```
npm install -D css-loader style-loader

```

**11. Add font in your webpack**

- To summarize, to avoid any font related errors with webpack, you need to:

1. Download file-loader.
2. Add it to your webpack config.
3. Import whatever fonts you wish to use into your CSS or SCSS files.

**12. Add prop-types in your webpack**

- Used for when we are checking our prop types in child component.

```
npm install -D prop-types
```
