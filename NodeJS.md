# Node JS

<a href="https://cdn.freebiesupply.com/logos/large/2x/nodejs-1-logo-png-transparent.png">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://cdn.freebiesupply.com/logos/large/2x/nodejs-1-logo-png-transparent.png" />
    <img src="https://raw.githubusercontent.com/nvm-sh/logos/HEAD/nvm-logo-color.svg" height="50" alt="nvm project logo" />
  </picture>
</a> &nbsp;&nbsp; 
<a href="https://github.com/nvm-sh/logos">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/nvm-sh/logos/HEAD/nvm-logo-white.svg" />
    <img src="https://raw.githubusercontent.com/nvm-sh/logos/HEAD/nvm-logo-color.svg" height="50" alt="nvm project logo" />
  </picture>
</a>&nbsp; &nbsp; 
<a href="https://andrejgajdos.com/wp-content/uploads/2019/11/npm-logo.png?x24361">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://andrejgajdos.com/wp-content/uploads/2019/11/npm-logo.png?x24361" />
    <img src="https://raw.githubusercontent.com/nvm-sh/logos/HEAD/nvm-logo-color.svg" height="50" alt="nvm project logo" />
  </picture>
</a>

## Installation Links

### Xampp Install: [Xamp Link](https://sourceforge.net/projects/xampp/files/XAMPP%20Windows/7.4.33/xampp-windows-x64-7.4.33-0-VC15-installer.exe/download)

### Composer Install: [Composer Link](https://getcomposer.org/Composer-Setup.exe)

### NVM Install: [Github](https://github.com/nvm-sh/nvm)

### Node Install: [Node 16.19.1](https://nodejs.org/download/release/v16.19.1/node-v16.19.1-x64.msi)

### Node Documentation: [Docs](https://nodejs.org/docs/latest-v18.x/api/)

---
## NPM Commands

```shell
npm help
```  
> See all npm commands


```shell
npm install module_name
```  
> Install a dependence, you can also use npm i module_name

```shell
npm install module_name -D
```  
> Install a Development dependence

```shell
npm unninstall module_name
```  
> Remove dependence

```shell
npm update
```  
> Update modules

```shell
npm audit
```  
> Identifies and reports security vulnerabilities in project dependencies.

```shell
npm run script
```  
> Executes a custom command or task defined in `package.json` scripts.


---

## NVM Commands



```shell
nvm help
```  
> See all nvm commands

```shell
nvm install
```  
> Download and install a Node.js version `nvm install 16`

```shell
nvm unninstall
```  
> Unninstall a Node.js version `nvm unninstall 16`

```shell
nvm use
```  
> Use a specific Node.js version `nvm use 16`

```shell
nvm ls
```  
> List installed Node.js versions

``` shell
nvm -v
```  
> Display nvm's version
                   
---
### ES Native Modules vs CommonsJS

```shell
import { registerFormEvents } from "./components/contactFrosm.js";
```  
> ES Native Module

```shell
const fs = require('fs')
```  
> Common js (NodeJS)

### Exports
`const name = "Claudio";`
```shell
module.exports = {name};
```  
> Exporting object `name` so it can be imported afterwards

---

## Create Node Project

```shell
Npm init –y
```  
> -y creates a project with default settings, you can check it on
`package.json`
```
{
  "name": "my-project",
  "version": "1.0.0",
  "description": "",
  "main": "index.js",
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1"
  },
  "keywords": [],
  "author": "",
  "license": "ISC"
}
```

sdfsadf 