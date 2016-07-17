# JavaScript and Node.js tooling

<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
**Table of Contents**  *generated with [DocToc](https://github.com/thlorenz/doctoc)*

- [JavaScript and Node.js tooling](#javascript-and-nodejs-tooling)
  - [Editor](#editor)
    - [Sublime Text 3](#sublime-text-3)
  - [IDE](#ide)
  - [Usando diferentes versiones de Node](#usando-diferentes-versiones-de-node)
  - [Linter](#linter)
    - [Agregando tu linter a Sublime Text](#agregando-tu-linter-a-sublime-text)
  - [Tabs y formato](#tabs-y-formato)
  - [Administrador de procesos](#administrador-de-procesos)
  - [Debugging](#debugging)
    - [node-inspector](#node-inspector)
    - [iron-node](#iron-node)
  - [Platforms as a Service](#platforms-as-a-service)
  - [Integración continua](#integracion-continua)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

Una lista opinionada de recursos para el desarollo en JavaScript y Node.js. Para leer la versión en inglés ingresá [acá][readme-en].

## Editor
Hay bastantes alternativas que ofrecen syntax highlighting, plugins y son considerablemente livianos:
* [Sublime Text 3][sublime3]
* [Brackets][brackets]
* [Atom][atom]
* [Cloud9][cloud9]
* [Visual Studio Code][vscode]

La última opción, Cloud9, es un editor web pero definitivamente merece un vistazo.

### Sublime Text 3
Personalmente prefiero Sublime ya que es muy liviano y altamente personalizable. Incluso podés agregar un plugin llamado [Package Control][package-control] que simplifica la instalación y desinstalación de cualquier otro plugin que quieras agregar. Luego de instalarlo, apretando `Ctrl+Shift+p` debería aparecer una opción nueva que dice "Install Package".

## IDE
Hasta el momento no trabajé con ningún IDE en especial, pero si tuve la oportunidad de probar [Webstorm][webstorm] y lo recomiendo bastante para aquellos acostumbrados a trabajar con IDEs. Tené en cuenta que el consumo de recursos (tanto en memoria en general, y en CPU cuando analiza la solución) es bastante superior al de cualquier otro editor mencionado previamente.

## Usando diferentes versiones de node
Muchas veces resulta útil tener soporte multi-versión de Node ya que algunos proyectos pueden funcionar en las versiones 0.12 o 0.10 y otros únicamente en 0.8. La idea de tener varias instalaciones *manuales* tampoco es muy agradable. [NVM][nvm] es una gran herramienta para esos casos y también tiene soporte para [io.js][io.js].

## Linter
Olvidate de checkear manualmente todos los paréntesis que abrís o, incluso peor, tener que encontrarte con errores de sintaxis cuando tu proceso se ejecuta. Los linters están para ayudarte en estos casos. Dos buenas opciones son [JSHint][jshint] y [ESLint][eslint]. Personalmente prefiero ESLint ya que ofrece una configuración mucho más granular.

### Agregando tu linter a Sublime Text
Instalá (fijate cómo en [acá](#sublime-text-3)) el paquete `SublimeLinter` y después instalá el paquete correspondiente al linter de tu elección (`SublimeLinter-jshint` or `SublimeLinter-contrib-eslint`). Tal vez debas cerrar y volver a abrir Sublime para que los cambios tomen efecto.

## Tabs y formato
Chequeando por espacios antes de palabras reservadas o después de cada paréntesis manualmente es una pérdida de tiempo. Lo mismo aplica a indentar manualmente las líneas de código, incluso las que copiás y pegás. [JavaScript Beautify][js-beautify] es una genial herramienta para resolver estos casos manualmente y también es configurable a tu estilo de programación. Instlá el paquete en Sublime Text y luego deberías poder ejecutarlo presionando `Ctrl+Alt+f`.

## Administrador de procesos
Si tu aplicación dispara alguna *uncaught exception*, lo más probable es que no quieras iniciar la aplicación nuevamente de una forma manual. Las siguientes opciones reiniciarán tu proceso si sucede algo malo:

- [upstart][upstart]
- [forever][forever]
- [supervisor][supervisor]
- [PM2][pm2]

En el caso de supervisor, no solo reinicia tu aplicación ante algún error no atrapado, sino que también reinicia la aplicación si modificás cualquier archivo de código de tu server para que las modificaciones se apliquen.

Las primeras tres opciones son simples y sólo apuntan a una funcionalidad específica, mientras que PM2 ofrece muchas otras funcionalidades cómo monitoreo de CPU, herramientas de log y balanceo de carga.

## Debugging
Si  te es familiar, encontrarás la interfaz de debugging nativa de familiar de alguna forma (`node debug app.js`). Para una interfaz gráfica de debugging podés utilizar [node-inspector][node-inspector] o [iron-node][iron-node]. Mientras node-inspector existe hace un tiempo, iron-node es considerablemente nuevo y, lo más importante, utilizan diferentes enfoques técnicos. 

### node-inspector
node-inspector abrirá una tab de Google Chrome en la cuál podés utilizar las [Chrome Dev Tools][chrome-dev-tools] para debuggear tu aplicación. Básicamente va a ejecutar tu aplicación Node y atachar los eventos entre tu proceso y las Dev Tools de Chrome.

### iron-node
iron-node está utilizando [electron][electron], lo cual le dá una sensación de livianez y una carga inicial más rápida. Por esa razón, ejecutará con su propia instalación de Node (io.js) y tendrá cómo resultado una compatibilidad con los módulos nativos un poco engorrosa.

## Platforms as a Service
Existen varias soluciones que incluyen instancias con la cuenta gratuita cómo:

- [OpenShift][openshift]
- [Heroku][heroku]
- [DigitalOcean][digitalocean]
- [Modulus][modulus]
- [Microsoft Azure Web Apps][azure]

## Continuous Integration
Hay varias opciones que incluyen servicios gratuitos para proyectos Open Source cómo:

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
[readme-en]: README.md
[readme-es]: README-es.md
[circle-ci]: https://circleci.com/
[circle-ci]: https://circleci.com/

------------------

Contributions and suggestions are welcome! Just open an issue or a pull request.
