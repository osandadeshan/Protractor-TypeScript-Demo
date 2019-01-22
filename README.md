# Protractor TypeScript Demo

Typescript provides code auto completion and helpful hints with a text editor like Microsoft's Visual Studio Code or another text editor with Typescript support.

Note that this example uses TypeScript 2.0.

## Examples

This example demonstrates how you should use page object model design pattern with Protractor and TypeScript.

## File organization

```
Protractor-TypeScript-Demo/
|- node_modules/             // downloaded node modules
|- compiled_typescript/      // compiled javascript output
|
|- .gitignore                // since typescript produces javascript, we should not commit javascript to the repo
|- page/angularPage.ts       // page object example
|- conf.ts                   // configuration for the page objects example
|- package.json              // node dependencies for the project
|- README.md                 // this file
|- spec/angularPageSpec.ts   // spec for the page objects example
|- tsconfig.json             // typescript transpile configuration
```


## Getting started

This package.json references the local protractor directory with `"protractor": "file: ../"`. For the type declarations to work, from the protractor directory run an `npm install` to generate the declarations file.

Next, install the node_modules with:

```
npm install
```


## Protractor typings

To use Protractor types, you'll need to import `protractor`. After this is imported, you should have autocompletion hints when typing.

```
import {browser, element, by, By, $, $$, ExpectedConditions} from 'protractor';
```

Although the Protractor configuration file can be written in javascript, creating it in typescript will have some hints. These hints and the reference configuration can be found in `lib/config.ts`. Below we are importing the Config interface and applying that interface to the config variable:

```
import {Config} from 'protractor';

export let config: Config = {
  ...
}
```

## Ambient typings

Protractor also uses ambient types including jasmine, jasminewd2, and node. These are brought in via the `tsconfig.json` file, which uses npm module resolution to get types from `node_modules/@types`.

If you are using the jasmine framework for your tests, make sure to do:

```
npm install --save-dev @types/jasmine @types/jasminewd2
```

## Compiling your code

To convert your typescript to javascript (transpiling), you'll use the Typescript compiler (tsc). To istall it use this command 
```
npm install typescript -g
```
If you install typescript globally, the command is `tsc`. If it is not installed globally, the typescript compiler can be executed with `npm run tsc`.

## Running Protractor

After transpiling your code to javascript, you'll run Protractor like before: `protractor ./compiled_typescript/conf.js`

## Helpful links

* [TypescriptLang.org tutorial](http://www.typescriptlang.org/docs/tutorial.html)
* [TypescriptLang.org tsconfig.json](http://www.typescriptlang.org/docs/handbook/tsconfig-json.html)
* [Typescript gitter](https://gitter.im/Microsoft/TypeScript)
* [Typescript stackoverflow](http://stackoverflow.com/questions/tagged/typescript)
