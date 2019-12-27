### Q. What is asynchronous programming?

A form of parallel programming that allows the main thread to work independently of the subtasks in other threads. The threads then respond to say whether the operation has succeeded or not.

This seems like a good article on promises (much like Rust's `Result<O, E>`): https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Asynchronous/Promises

### Q. What philosophies are there in managing software projects?

#### Test-driven development (TDD)

Source: https://en.wikipedia.org/wiki/Test-driven_development

Development cycle is short. Requirements are turned into highly specific test cases, for which software must pass in order to be released. TDD uses unit tests that test highly specific functionality.

To cover integrations, e.g. with databases, web services, unit testing should be separately enforced for each process. An interface is defined to describe the access available (using Dependency Inversion Principle), and is implemented using mock objects which simulate the actual resource being accessed with pre-defined data.

#### Behaviour-driven development (BDD)

Source: https://en.wikipedia.org/wiki/Behavior-driven_development

Offshoo of TDD to negotiate between business requirements and technical requirements, typically used in Agile development. BDD involves specifying and testing of desired behaviour itself, which is coded as a user story with different user scenarios (desired outcome of event in given context). For example,

```
Narrative
    As a (person or role who will benefit from the feature),
    I want (the feature),
    so that (the benefit of the feature).

Acceptance criteria
    Given (the initial context at the beginning of the scenario),
    when (the event that triggers the scenario),
    then (the expected outcome).
```

#### Systems modeling

Commonly used is Unified Modeling Language (UML) in software engineering to visualize the design of a system.
Read up on the topic of engineering design.

#### Software documentation

User documentation can be presented in three broad ways:
1. Tutorial: Step-by-step guide to accomplishing tasks, for new users
2. Thematic: Consolidation of chapters relevant to use case, e.g. troubleshooting
3. Reference: List of commands, often cross-indexed

#### Continuous integration and delivery (CI/CD)

Continuous integration requires developers to merge frequently. Involves automated unit testing on local machine, a build server which compiles the code periodically and perform quality control tests, e.g. static analysis, profiling, documentation extraction.

Continuous delivery represents the rest of the deployment pipeline up until release, where the compilance of the system to business requirements is tested, either through automated tests or user acceptance tests. This ensures the development team receives adequate and timely feedback.

### Q. How are node modules managed in projects? What does a project directory look like?

#### Installation directory for npm

Apparently `npm` is pretty much like `git`, creates packages in local directory (unless specified globally). See [SO](https://stackoverflow.com/questions/5926672/where-does-npm-install-packages).

```cmd
npm install <package_name>   % install package in local directory
npm root                     % specify effective installation directory
npm list -g                  % list packages in global directory
```

`yarn` can be run compatibly with `npm`.


#### npm package directory

From a [list](https://github.com/sindresorhus/awesome-nodejs) of NodeJS modules, came across [Gulp](https://github.com/gulpjs/gulp). Package dependencies are specified in the [package.json](https://github.com/gulpjs/gulp/blob/master/package.json) file, with explanations for how it is handled [here](https://docs.npmjs.com/files/package.json). Turns out `yarn` can automatically add it for you using the [add](https://yarnpkg.com/en/docs/managing-dependencies#toc-adding-a-dependency) command.

```json
{
  "main": "index.js",
  "files": [
    "LICENSE",
    "index.js",
    "bin"
  ],
  "dependencies": {
    "glob-watcher": "^5.0.3",
    "gulp-cli": "^2.2.0",
    "undertaker": "^1.2.1",
    "vinyl-fs": "^3.0.0"
  },
  "devDependencies": {
    "coveralls": "github:phated/node-coveralls#2.x",
    "eslint": "^2.13.1",
    "mocha": "^3.0.0",
    "nyc": "^10.3.2"
  }
}
```

[webpack](https://github.com/webpack/webpack) looks to be pretty complete, with `bin`, `lib` to group function calls for main (or `packages` in [Meteor](https://github.com/meteor/meteor/tree/devel/packages)), `setup`, `test`, `tooling`. `benchmark` used to quantify startup performances. References to dependencies are requested using:

```javascript
const path = require("path");
const fs = require("fs");
const ts = require("typescript");
```

Turns out `require` is a scoping feature of NodeJS, functioning as modules.

### Q. What is Model-View-Controller (MVC)?

Source: https://www.tutorialsteacher.com/mvc/mvc-architecture

The MVC architecture separates the application into three separate components:
- Model retrieves and maintains the application state and logic
- View is the user interface that displays data from the model to the user
- Controller handles the user request arriving from the view, which modifies the state and renders the view accordingly.

From the DIP article on Wikipedia, the controller can be seen as an interface between the model and the view, to prevent overly tight coupling between the UI and the logic.

### Q. What is NodeJS even?

Source: https://stackoverflow.com/questions/9901082/what-is-this-javascript-require

Javascript is originally confined to a web browser with limited global context. Server-side Javascript eliminates that restriction to allow Javascript to be called into native code and open sockets.

NodeJS is typically used for non-blocking operations on the server.

### Q. What is linting?

Code review to ensure it has consistent style. Some examples include [StandardJS](https://standardjs.com/), [ESLint](https://eslint.org/). According to a list of solutions to resolve a callback hell (interesting [website](http://callbackhell.com/)), a linter can help identify all the errors needed to be handled.

### Q. How bypass CORS blocking when retrieving data?

Some resources here might here:
- https://www.html5rocks.com/en/tutorials/cors/
- https://www.moxio.com/blog/12/how-to-make-a-cross-domain-request-in-javascript-using-cors#alternatives
- How did CORS come about: https://hacks.mozilla.org/2009/07/cross-site-xmlhttprequest-with-cors/
- https://www.moxio.com/blog/12/how-to-make-a-cross-domain-request-in-javascript-using-cors

### Q. How to setup continuous integration?

No idea.
