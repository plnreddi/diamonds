![Diamonds Logo](http://vodbro.com/diamondstack.png?zz1)

<sub>**LOL:** *All rights belong to their respective project owners where those owners do not endorse or
directly support this project except by what is implied or permitted by their open source software licenses.
Diamonds was created out of limited need for a startup of mine, so utilize considering that reality.
Its very particular in two concerns: security and scaling performance over the usual 'universal' cms gambit.
Yet feel it is potentially universal as it grows to adapt.*</sub>

## The Super Web Stack

**Diamonds** are coupled client/server apps composed of Compound, Angular, Polymer, and Famo.us Yeoman generators forming a super HMVC-to-MVVM web & device development stack in full. And yes while Compound alone's a "full stack" solution we found it didn't do things that Angular does bindingly bright *in browser* nor clairvoyantly adept like Polymer nor targets the emergent UI/X plural device standards of Material Design metaphors. While Compound has a strong performance backend its PolyFAng siblings all delegate to a myriad of specialized server platform options making the marriage of Diamonds' poly spouses most ideal.

## NPM Installation

<sup>**Also installs:**: angular, closure-compiler, compound, compound-passport, co-socket, famous, famous-angular, generator-famous-angular, generator-polymer, jugglingdb, jugglingdb-redis, passport, pm2, redis, redis-hq-adapter, sass, web-component-tester, and yo.</sup>

App install requires about 900MB

**Run:** 

1. $> npm install diamonds; 
2. $> diamonds &lt;YourAppName&gt;
3. $> diamonds [test|deploy|gen]
 
Our meta generator will start by executing 'compound-init <YourAppName>' 
script installing Compound and patching it for Diamonds. In order to co-create
Angular components a new Compound app will be created called "Diamonds" exposing JugglingDB's ORM API, view files, along with crud controller & nested routes.

Then script 'yo-init' initialize the Angular/Famo.us and Polymer apps using custom ejs chrome and view 
partials while mapping Angular dependency injection to the Compound controller for realtime integrated 
data binding instead of Compound's basic approach.
[? Additionally angular_node_bind is used to monitor Node.bind() of Polymer model activity 
and emit to tandem Angular apps.]

The four projects share same directory with Angular in "aapp/', Famo.us in "fapp/", Polymer in "papp/", 
with Compound in "capp/" keeping code & resources separate.

## Diamonds Usage

$> diamonds test|deploy|(generate|remove element &lt;name&gt;[:*type* | :*default* | :*index*]); 

**Options**
*    type = "***Date|Number|Boolean|Text|String***" (default: string) 
* default = "default value" (default: null)
*   index = "true|false" (default: false)
*All element names are prefixed 'Dia-' for clarity.*

Example: $> *diamonds generate element recordTime:Date default=Date.now index=true;* 

Launch and view app at http://&lt;host&gt;:8080/

## Edges and Origin API(s)

Each Diamond has unique origin API server(s) along with list of authorized edge workers.
By default Diamonds' origin will use a generic Redis store installed before or during Diamonds if missing. 
Diamonds' Redis will come configured for local-only, no pw, DB:2 on :6379._ but most vendors have drivers for origin storage (See JugglingDB).
Origin (aka Compound) performs *backyarding* of lapsed TTL Redis keys to an online SQL local or network db. 
This ensures dormant data aren't squandering server memory yet remain speedily available via SQL.

Edge workers generally provide a rate-limited hyper-consistent cache and queuing 'dumb' API. 
This is done in our edge configuration via PHP & LevelDB ***sharded*** strategy for replication and isolation. 
In edgeless configs you can use local API queuing via Node & Redis or SQL-only if scaling isn't a concern. 
Their edge behavior ensures a peformance enhancing shared-nothing data architecture while serially pushing 
queued edge client data & queries to origin leaving it incorruptable and removed from adding to back pressure.

Or if you want to publicly expose your origin API just intending to use a single machine you can
set origin equal to worker forgoing edgewise optimization altogether. 

## Vulcanize
*Polymer's Web Component build tool*
...
## Closure Compiler
*Angular's Production JS optimizer*
...

## Deploy
1. `$> grunt build; # results in < project >/dist `
2. `$> diamonds deploy; # -> pm2 start server.js -i 3 --name <DimaondApp>` ...

Now view app at http://&lt;host&gt:8080/

## Project Home
- Here & NPM

## Source Projects
- [Yo](yeoman.io)
- [Compound](https://github.com/1602/compound) [Docs](http://compoundjs.com/docs/)
- [Angular](angularjs.org)
- [Polymer](www.polymer-project.org)
- [Polymer Designer](http://polymer-designer.appspot.com)
- [Closure Compiler](github.com/google/closure-compiler)
- [Passport](passportjs.org)
- [Famous](famo.us) [Docs](https://famo.us/docs/)
- Material Design [Polymer](https://www.polymer-project.org/docs/elements/material.html),  [Angular](https://material.angularjs.org/), [Intro](http://www.google.com/design/spec/material-design/introduction.html)
- [PM2](https://github.com/Unitech/pm2)

## Credits 
- Eric Bidelman's [Angular Using Polymer Elements](https://www.youtube.com/watch?v=p1NpZ-0Op0w)
- Web Components [Angular-Polymer Interop](https://github.com/webcomponents/angular-interop)
- [NG-Polymer-Elements](http://ngmodules.org/modules/ng-polymer-elements)

## Licenses
MIT, BSD
