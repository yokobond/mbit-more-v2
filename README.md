<h1 align="center">Microbit More v2</h1>
<p>
  <img alt="Version" src="https://img.shields.io/badge/version-0.2.2-blue.svg?cacheSeconds=2592000" />
  <a href="https://yokobond.github.io/mbit-more-v2" target="_blank">
    <img alt="Documentation" src="https://img.shields.io/badge/documentation-yes-brightgreen.svg" />
  </a>
  <a href="https://github.com/yokobond/mbit-more-v2/graphs/commit-activity" target="_blank">
    <img alt="Maintenance" src="https://img.shields.io/badge/Maintained%3F-yes-green.svg" />
  </a>
  <a href="https://github.com/yokobond/mbit-more-v2/blob/master/LICENSE" target="_blank">
    <img alt="License: MIT" src="https://img.shields.io/github/license/yokobond/mbit-more-v2" />
  </a>
</p>
<p>
  <img alt="work with micro:bit v1 and v2" src="https://cdn.sanity.io/images/ajwvhvgo/production/17d9277789c6f781092ee9c2f6993b0457c6ce94-1454x421.png" height="48">
</p>

> Full-functional extension of micro:bit for Scratch3

### ✨ Open [Microbit More](https://microbit-more.github.io/)

This is a mod application from [Scratch3 by MIT](https://scratch.mit.edu/). You can code using 'Microbit More' and all blocks in nomal Scratch3 on this app. 
The program of micro:bit for Microbit More is [yokobond/pxt-mbit-more-v2](https://yokobond.github.io/pxt-mbit-more-v2/).

You don't need to run [Scratch Link](https://scratch.mit.edu/microbit) when your browser is Chrome, Edge or 'Web Bluetooth API' supporting one (the browser in Chromebook, [‎Bluefy](https://apps.apple.com/jp/app/bluefy-web-ble-browser/id1492822055) in iPadOS, like that).

## Setup Development Environment

Use [yokobond/scratch-gui at xcratch](https://github.com/yokobond/scratch-gui/tree/xcratch) as a base scratch-gui if you use Web Bluetooth feature.

(This extension works well on "LLK/scratch-gui". But the normal Scratch does not have Web Bluetooth feature. So you have to launch "Scratch Link" with normal Scratch.)

```sh
git clone -b xcratch https://github.com/yokobond/scratch-gui.git
cd ./scratch-gui
npm install
npm install https://github.com/yokobond/scratch-vm.git#xcratch
```

Download the Scratch3 repositories according to the supposed directory configuration.

```
.
|-- mbit-more-v2
|-- scratch-gui
```

Install node modules and setup to use local repo for development.

```sh
cd ./mbit-more-v2
npm install
npm run setup:local
npm run register:local
```

## Register in self-build Scratch3

To register this extention in your self-build Scratch3 based on Xcratch, execute `scripts/register.js` with options as follows.

```sh
node ./scripts/register.js --id=microbitMore --gui="../scratch-gui"
```

When you use the normal "LLK/scratch-gui", register with `--base=LLK`.

CAUTION: The normal "LLK/scratch-gui" doesn't have Web Bluetooth featur.

```sh
node ./scripts/register.js --id=microbitMore --gui="../scratch-gui" --base=LLK
```

register.js accepts these commandline arguments.

- --base : base code to register in (optional, availables: "LLK")
- --link : use symbolic link instead of copy sources
- --id : extensionID of this extension
- --block : location of block files from current dir (optional, default: "./src/block")
- --entry : location of entry files from current dir (optional, default: "./src/ently")
- --dir : directory name of the extension will be copied (optional, default: extensionID)
- --gui : location of scratch-gui from current dir (optional, default: "../scratch-gui")
- --vm : location of scratch-vm form current dir (optional, default: "gui/node_modules/scratch-vm")
- --url : URL to get this module as a lodable extension for Xcratch (optional)
- -C : make the extension as a member of core-extensions

**CAUTION:** register-script will change '`extension default`' in `scratch-gui/src/lib/libraries/extensions/index.jsx` as follows.

change from the original code

```js
export default [...];
```

to

```js
const extensions = [...];
export default extensions;
```

It may break registration mechanism of the other user-made extensions.


## Xcratch Module Building

Build module as loadable extension for [Xcratch](https://github.com/yokobond/xcratch).

```sh
node ./scripts/build.js --name=microbitMore --block="./src/block" --entry="./src/entry" --gui="../scratch-gui" --output="./dist"
```

build.js accepts these commandline arguments.

- --name: name of the module file (without '.mjs')
- --block : location of block files from current dir
- --entry : location of entry files from current dir
- --gui : location of scratch-gui from current dir (optional, default: "../scratch-gui")
- --vm : location of scratch-vm form current dir (optional, default: "gui/node_modules/scratch-vm")
- --url : URL to get its module as a lodable extension for Xcratch (optional)
- --output : location to save module form current dir (optional, default: "./build")


## Author

👤 **Koji Yokokawa**

* Website: http://www.yengawa.com/
* Github: [@yokobond](https://github.com/yokobond)

## 🤝 Contributing

Contributions, issues and feature requests are welcome!<br />Feel free to check [issues page](https://github.com/yokobond/mbit-more-v2/issues). You can also take a look at the [contributing guide](https://github.com/yokobond/mbit-more-v2/blob/master/CONTRIBUTING.md).

## Show your support

Give a ⭐️ if this project helped you!


## 📝 License

Copyright © 2020-2021 [Koji Yokokawa](https://github.com/yokobond).<br />
This project is [MIT](https://github.com/yokobond/mbit-more-v2/blob/master/LICENSE) licensed.

***
_This README was generated with ❤️ by [readme-md-generator](https://github.com/kefranabg/readme-md-generator)_