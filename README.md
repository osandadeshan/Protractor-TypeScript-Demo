# Protractor TypeScript Demo

<br />

## What is Protractor?

Protractor plays an important role in the Testing of AngularJS applications and works as a Solution integrator combining powerful technologies like Selenium, Jasmine, Web driver, etc. 

It is intended not only to test AngularJS application but also for writing automated regression tests for normal Web Applications as well.

<br />

## Why do we need Protractor framework?

JavaScript is used in almost all web applications. As the applications grow, JavaScript also increases in size and complexity. In such case, it becomes a difficult task for Testers to test the web application for various scenarios.

Sometimes it is difficult to capture the web elements in AngularJS applications using JUnit or Selenium WebDriver.
Protractor is a NodeJS program which is written in JavaScript and runs with Node to identify the web elements in AngularJS applications, and it also uses WebDriver to control the browser with user actions.

<br />

## Why can't we find Angular JS web elements using normal Selenium web driver?

Angular JS applications have some extra HTML attributes like ng-repeater, ng-controller, ng-model.., etc. which are not included in Selenium locators. Selenium is not able to identify those web elements using Selenium code. So, Protractor on the top of Selenium can handle and controls those attributes in Web Applications.

The protractor is an end to end testing framework for Angular JS based applications. While most frameworks focus on conducting unit tests for Angular JS applications, Protractor focuses on testing the actual functionality of an application.

<br />

## Protractor installation

(Steps 3 and 4 are Optional but recommended for better practice).

   1. Open command prompt and type `npm install –g protractor` and hit Enter.
      The above command will download the necessary files and install Protractor on the client system.

   2. Check the installation and version using `protractor --version`. If successful it will show the version.

   3. Update the Web driver manager. The web driver manager is used for running the tests against the angular web application in a specific browser. After Protractor is installed, the web driver manager needs to be updated to the latest version. This can be done by running the following command in the command prompt.\
      `webdriver-manager update`

   4. Start the web driver manager. This step will run the web driver manager in the background and will listen to any tests which run via protractor.
   Once Protractor is used to run any test, the web driver will automatically load and run the test in the relevant browser. To start  the web driver manager, the following command needs to be executed from the command prompt.\
   `webdriver-manager start`

   Now, if you go to the following URL (http://localhost:4444/wd/hub/static/resource/hub.html) in your browser, you will actually see the Web driver manager running in the background.

<br />

## TypeScript

Typescript provides code auto completion and helpful hints with a text editor like Microsoft's Visual Studio Code or another text editor with Typescript support.

Note that this example uses TypeScript 2.0.

<br />

## Examples

This example demonstrates how you should use page object model design pattern with Protractor and TypeScript.

<br />

## File organization

```
Protractor-TypeScript-Demo/
|- node_modules/             // downloaded node modules
|- compiled_typescript/      // compiled javascript output
|- .gitignore                // since typescript produces javascript, we should not commit javascript to the repo
|- page/angularPage.ts       // page object example
|- conf.ts                   // configuration for the page objects example
|- package.json              // node dependencies for the project
|- README.md                 // this file
|- spec/angularPageSpec.ts   // spec for the page objects example
|- tsconfig.json             // typescript transpile configuration
```

<br />

## Getting started

This package.json references the local protractor directory with `"protractor": "file: ../"`. For the type declarations to work, from the protractor directory run an `npm install` to generate the declarations file.

Next, install the node_modules with:

```
npm install
```

<br />

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

<br />

## Ambient typings

Protractor also uses ambient types including jasmine, jasminewd2, and node. These are brought in via the `tsconfig.json` file, which uses npm module resolution to get types from `node_modules/@types`.

If you are using the jasmine framework for your tests, make sure to do:

```
npm install --save-dev @types/jasmine @types/jasminewd2
```

<br />

## Compiling your code

To convert your typescript to javascript (transpiling), you'll use the Typescript compiler (tsc). To istall it use this command 
```
npm install typescript -g
```
If you install typescript globally, the command is:
```
tsc
```
If it is not installed globally, the typescript compiler can be executed with:
```
npm run tsc
```

<br />

## Running Protractor

After transpiling your code to javascript, you'll run Protractor like before: 
```
protractor ./compiled_typescript/conf.js`
```

<br />

## Helpful links

* [TypescriptLang.org tutorial](http://www.typescriptlang.org/docs/tutorial.html)
* [TypescriptLang.org tsconfig.json](http://www.typescriptlang.org/docs/handbook/tsconfig-json.html)
* [Typescript gitter](https://gitter.im/Microsoft/TypeScript)
* [Typescript stackoverflow](http://stackoverflow.com/questions/tagged/typescript)
