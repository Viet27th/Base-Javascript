> https://www.tsmean.com/articles/how-to-write-a-typescript-library/

# 1. Development
## Installation
```sh
yarn install
```
-----

## Build
For production release:
```sh
yarn build
```

# 2. Tech
## tsconfig.json
- `"declaration": true` - This will generate the .d.ts files (aka declaration files) which contain the types of your code.
- `"module": "commonjs"` - The **module compiler option**. It is required if you want your code to run seamlessly with most current Node.js applications. We tell the compiler that by default we want our module declaration to be in commonjs syntax. This will compile every `import` and `export` into `require()` and `module.exports` declarations, the default syntax in a Node environment. Replace this with `"module": "esnext"` if you're building a library for the browser.
- `"target": "es2015"` - Specifies which version of JavaScript your code will get transpiled to.
- `"outDir": "./dist"` - Will write your compiled files into the **dist** folder and the include option specifies where your source code lives.
-----

## package.json
- `"types": "dist/index.d.ts"` - To declare where to find the type declarations. Otherwise the consumer won't find your module.
- `"files"` - Helps you to whitelist the files you want to ship to the npm registry. This is usually a much easier and safer route than using the `.npmignore` file.
- `"peerDependencies"` - This means if you install this library you also need to install the libraries declared inside **peerDependencies**
