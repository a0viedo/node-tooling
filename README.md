# JavaScript and Node.js tooling

<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
**Table of Contents**  *generated with [DocToc](https://github.com/thlorenz/doctoc)*

- [JavaScript and Node.js tooling](#javascript-and-nodejs-tooling)
  - [Editor](#editor)
    - [Sublime Text 3](#sublime-text-3)
  - [IDE](#ide)
  - [Using different versions of Node](#using-different-versions-of-node)
  - [Linter](#linter)
    - [Adding your linter to Sublime Text](#adding-your-linter-to-sublime-text)
  - [Tabs and format](#tabs-and-format)
  - [Process Manager](#process-manager)
  - [Debugging](#debugging)
    - [node-inspector](#node-inspector)
    - [iron-node](#iron-node)
  - [Platforms as a Service](#platforms-as-a-service)
  - [Continuous Integration](#continuous-integration)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->



An opinionated list of resources for JavaScript and Node.js development. You can find the Spanish version [here][readme-es].

## Editor
There're very good options with syntax highlighting and support for plugins:
* [Sublime Text 3][sublime3]
* [Brackets][brackets]
* [Atom][atom]
* [Cloud9][cloud9]
* [Visual Studio Code][vscode]

The last option, Cloud9, it's a web-based editor but it definitely deserves a try.

### Sublime Text 3
I personally prefer Sublime because it's lightweight and highly configurable. You can add a [Package Control][package-control] plugin to install any other plugin to Sublime by pressing `Ctrl+Shift+p`.

## IDE
I haven't used any IDE while working on Node projects, but I have tried and would recommend [Webstorm][webstorm]. Keep in mind that will require much more memory than any editor mentioned before.

## Using different versions of Node
Is often useful to have multi-version support of Node because there are some projects that might work on newer releases but not in 0.10 for example, or vice versa. [NVM][nvm] is a great tool for that and it also has support for [io.js][io.js].

## Linter
Forget about manually checking all the parenthesis you open or even worst, having to deal with them as your process gets executed. Two good options are [JSHint][jshint] and [ESLint][eslint]. I personally prefer ESLint because it offers a more granular configuration.

### Adding your linter to Sublime Text
Install the package (see [Sublime Text 3](#sublime-text-3)) `SublimeLinter` and then install the package of your linter (`SublimeLinter-jshint` or `SublimeLinter-contrib-eslint`). Might have to restart your editor for the changes to take effect.

## Tabs and format
Checking for spaces before or after every parenthesis is a waste of time. Same goes for manually indenting any new line if your code, even if it's copy & pasted. [JavaScript Beautify][js-beautify] is a great tool for doing that automatically and is also configurable. Install the package in Sublime Text and after that you will be able to run it by pressing `Ctrl+Alt+f`.

## Process Manager
If some uncaught exception fires in your application, you will probably don't want to start the application again manually. The following options will watch your application process and restart it if something goes wrong:

- [upstart][upstart]
- [forever][forever]
- [supervisor][supervisor]
- [PM2][pm2]

In the case of supervisor, not only will restart the application if an uncaught exception occurs, but will also restart your application if you modify any server-side file for the modifications to take effect.

The first three options are simple and they only try to focus on a single feature, while PM2 offers a lot more functionalities like CPU monitoring, log facilities and load balancing.

## Debugging
If you're familiar with [gdb][gdb], you will find the native debugging interface somewhat familiar (`node debug app.js`). For graphical debugging interfaces you could use [node-inspector][node-inspector] or [iron-node][iron-node]. While node-inspector has been around for a while, iron-node is considerably new, but most important, they have different approaches. 

### node-inspector
node-inspector will open up a Chrome tab in which you can use the [Chrome Dev Tools][chrome-dev-tools] to debug your application. It's important to notice that will run your process in debug mode and attach to it.

### iron-node
iron-node is using [electron][electron], which gives an impression of being faster to load up. Because of that, it will run with its own Node installation (io.js) and as a result the compatibility with native modules can be a little bit tricky.

## Platforms as a Service
Many solutions include several instances with a free account like:

- [OpenShift][openshift]
- [Heroku][heroku]
- [DigitalOcean][digitalocean]
- [Modulus][modulus]
- [Microsoft Azure Web Apps][azure]

## Continuous Integration
There are several options that include free services to Open Source projects such as:

- [Travis CI][travis-ci]
- [Jenkins CI][jenkins-ci]
- [Codeship][codeship]
- [CircleCI][circle-ci]


[io.js]: https://iojs.org/en/index.html
[sublime3]: http://www.sublimetext.com/3
[brackets]: http://brackets.io/
[atom]: https://atom.io/
[cloud9]: https://c9.io/
[vscode]: https://code.visualstudio.com/
[package-control]: https://packagecontrol.io/
[nvm]: https://github.com/creationix/nvm
[jshint]: http://jshint.com/
[eslint]: http://eslint.org/
[js-beautify]: https://packagecontrol.io/packages/Javascript%20Beautify
[openshift]: https://www.openshift.com/
[heroku]: https://heroku.com/
[digitalocean]: https://www.digitalocean.com/
[modulus]: https://modulus.io/
[azure]: http://azure.microsoft.com/
[pm2]: https://github.com/Unitech/pm2
[supervisor]: https://github.com/Supervisor/supervisor
[upstart]: https://github.com/cvee/node-upstart
[forever]: https://github.com/foreverjs/forever
[webstorm]: https://www.jetbrains.com/webstorm/
[electron]: https://github.com/atom/electron
[gdb]: http://www.gnu.org/software/gdb/
[iron-node]: https://github.com/s-a/iron-node
[node-inspector]: https://github.com/node-inspector/node-inspector
[chrome-dev-tools]: https://developer.chrome.com/devtools
[codeship]: https://codeship.com/
[jenkins-ci]: https://jenkins-ci.org/
[travis-ci]: https://travis-ci.org/
[readme-es]: README-es.md
[circle-ci]: https://circleci.com/

------------------

Contributions and suggestions are welcome! Just open an issue or a pull request.
