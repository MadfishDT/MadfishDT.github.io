## Typescript Nodejs Setting

* Nodejs Development Environment Setting with Typescript

## Reference

- [express typescript](https://novemberde.github.io/node/2017/10/22/Express-Typescript.htm)

## Make Package.json
- make package.json in project folder with your hand or 'npm init'
```
npm init
```
## Install Developments Packages

- npx: support using packags in project folder(node_module locally binary)
- nodemon: file change watcher
- typescript: typescript compiler
- webpack: bundle and minified 
- webapck-cli: webpack command line interface tool
- source-map-support: support typescript mapping file connect with compiled source
```
npm install -g npx
npm install --save-dev typescript ts-loader npm-run-all webpack nodemon webpack-cli
npm install --save express source-map-support
```

## Configuration Typescript

- make tsconfig.json file

if you use local project installed typescript
```
npx tsc --init
```

if you use global installed typescript 
```
tsc --init
```

tsconfig.json
```json
{
  "compilerOptions": {
     "lib": [
        "es5",
        "es6"
     ],
     "target": "es5",
     "module": "commonjs",
     "moduleResolution": "node",
     "outDir": "./build",
     "emitDecoratorMetadata": true,
     "experimentalDecorators": true,
     "sourceMap": true
  }
}
```

## Configuration Webpack

- make config directory 'project/config/'
- make webpakc.config.js

```javascript
const path = require('path');

module.exports = {
  entry: './src/main.ts', //entry source path
  module: {
    rules: [
      {
        test: /\.tsx?$/,
        use: 'ts-loader',
        exclude: /node_modules/
      }
    ]
  },
  devtool: 'source-map',
  target: 'node',
  resolve: {
    extensions: [ '.tsx', '.ts', '.js' ]
  },
  output: {
    filename: 'bundle.js',
    path: path.resolve(__dirname, 'dist')
  }
};
```

## Make Application Source Code

src/main.ts
```ts
class AppMain {
  public app: express.Application;


  constructor () {
    console.log(`I'm Main`);
  }
}

export default AppMain;
```

## Developing run Scrip && build Script

package.json
```json
....
 "scripts": {
    "start": "nodemon --watch src --delay 1 --exec ts-node src/main.ts",
    "build": "webpack --config config/webpack.config.js",
  },
```

## template code 
- [quick start typescript nodejs](https://github.com/MadfishDT/quickStartTSnode)


