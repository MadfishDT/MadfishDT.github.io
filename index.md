## Welcome to MadfishDT

## Knowledge
1. Typescript, Javascript, Web, PWAs

2. Elastic Search 
 - [Elastic Search Querys](/blogs/ES.md)
    - add data
    - remove data
    - remove index
    - no sql query
3. Python Tutorial
 - [Python Basic](/blogs/python_basic.md)

## Knowledge
1. [Typescript Nodejs Devleopment](/blogs/tsnode.md)
2. [MongoDB install on ubuntu](/blogs/MongoDB)
    - mongoDB queries

## Projects
You can use MadfishDT Contents and Source Codes

 1. TypeScript Projects
     
    - [zlibt for typescript](https://github.com/MadfishDT/zlibt) base on imaya zlib 
        - standard zlib support typescript, javascript
        - [npm zlibt](https://www.npmjs.com/package/zlibt)
    - [unzipt for typescript](https://github.com/MadfishDT/unzipt) base on imaya
        - standard unzip support typescript, javascript
        - [npm unzipt](https://www.npmjs.com/package/unzipt)
    - [unziptcli for typescript](https://github.com/MadfishDT/unziptcli) base on imaya
        - standard unzip support typescript, javascript
        - command line argument support
        - [npm unziptcli](https://www.npmjs.com/package/unziptcli)
    - [CommentRemovery](https://github.com/MadfishDT/CommentRemovery)
        - remove coments in codes
        - [npm CommentRemovery](https://www.npmjs.com/package/commentremovery)
    - [code-textizer](https://github.com/MadfishDT/codeTextizer)
        - convert code to text
        - code can asign string valriable in javascript, c++, c etcs....
        - [npm code-textizer](https://www.npmjs.com/package/code-textizer)
    - [objectwatchers](https://github.com/MadfishDT/objectwatcher)
        - javascript object and variable watch module
        - this module is not base on Event from browser and module
            - for example zone.js start search when Event occur in browser or module
            - My module re-define setter and getter and make polling variable
            - support typescript, javscript, nodejs, browser
        - [npm objectwatchers](https://www.npmjs.com/package/objectwatchers)

2. zlibjs full convert to typescript version with webpack
- [zlibt](https://github.com/MadfishDT/zlibt)
    - support typescript
    - support webpack bundling code
    - support all of zlibjs
        - PKZIP
        - Zlib(rawinflate, rawdeflate)
        - GZip
    - Comming soon 
    - support full bundle zlib, support partial bundle for user, want to only one operation
        - pkzip bundle
        - zlib bundle
        - gzip bundle
    - support UMD for pure web site
    - support nodejs
    - support typescript for angular, react ......
- [npm zlibt2](https://www.npmjs.com/package/zlibt2)

3. Chromium Projects
    - [electron customizing](https://github.com/MadfishDT/electron)
        - [electron build tips](/blogs/electron_tips.md)
        - [electron API enhancement 1: moveTop API](/blogs/electron_moveTop.md)
            - currently this API was merged in electron master branch.
            - BrwoserWindow [win.moveTop()](https://electronjs.org/docs/api/browser-window#winmovetop)
        - [electron API enhancement 2: setAspectRatio](/blogs/electron_setAspectRatio.md)
            - currently this API is evaluating in electron pull request to merge electron master branch
            - [win.setAaspectRatio](https://github.com/electron/electron/pull/18306)

4. Survey Portal
    - Create online Survey for admin
    - Provide Qustionary Service for user 
    - [dash Board](https://github.com/MadfishDT/dash-client2) <--Git link
        - Qustionary Portal Project
        - Vue, Bootstrap, SurveyJs
    - [dash Server](https://github.com/MadfishDT/dash-server) <--Git link
        - Nodejs, Express, Mysql Server
    - [Demo Site](http://35.193.127.219:8080)
    
## Next Projects

1. **Inline Worker Generator.**
    - support Webpack support web worker
        - worker module and module that use worker are bundled sinlge file, but worker working
    - support TypeScript, Javscript, nodejs(Electron) web worker
    - worker bundling support, you do not host 'worker.js'

2. **zipt**
- I have updata plan using with zlibt. provide partial bundle PKZIP, and provide nodejs interface and node cli mode Comming soon 
4. **embedding zlib, zip, unzip in electron**
5. node DMG make on uniz/linux  plateform by using dmglib
