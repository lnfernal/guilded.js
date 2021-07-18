<div align="center">
    <img src="https://raw.githubusercontent.com/lnfernal/guilded.js/main/static/readme-header.png" width="546" alt="guildedjs"/>
    <p><b>Tools for interacting with the <a href="https://www.guilded.gg/">Guilded.gg</a> API.</b></p>  
    <br />
    <p>
        <a href="https://discord.gg/jf66UUN"><img src="https://img.shields.io/discord/732714723744940032.svg?label=&logo=discord&logoColor=ffffff&color=7389D8&labelColor=6A7EC2 "></a>
        <img src="https://github.com/lnfernal/guilded.js/workflows/Linting/badge.svg" alt="Linting">
        <img src="https://github.com/lnfernal/guilded.js/workflows/TypeScript/badge.svg" alt="TypeScript">
        <a href="https://opensource.org/licenses/MIT"><img src="https://img.shields.io/badge/License-MIT-yellow.svg" alt="License: MIT"></a><br>
        <a href="https://github.com/lnfernal/guilded.js/issues"><img src="https://img.shields.io/github/issues-raw/lnfernal/guilded.js.svg?maxAge=25000" alt="Issues"></a>
        <a href="https://github.com/lnfernal/guilded.js/pulls"><img src="https://img.shields.io/github/issues-pr/lnfernal/guilded.js.svg?style=flat" alt="GitHub pull requests"></a><br>
    </p>
</div>

## 📝 About
> ### ⚠️ This library only works with selfbots, which are a gray zone in Guilded. Use at your own risk.

This repo serves as a monorepo that houses several packages, mainly the `guilded` package, which is a library for the Guilded API. Inspired heavily by [discord.js](https://github.com/discordjs/discord.js)

## 📦 Packages
* `js/guilded.js` (**[GitHub](https://github.com/lnfernal/guilded.js/tree/main/packages/guilded.js#readme), [NPM](https://www.npmjs.com/package/js/guilded.js)**) - main package that provides a lib for the guilded.gg API. Comes with built in caching, structures, etc.
* `js/guilded-api-types` (**[GitHub](https://github.com/lnfernal/guilded.js/tree/main/packages/guilded-api-typings#readme), [NPM](https://www.npmjs.com/package/js/guilded-api-typings)**) - thinking of making your own guilded lib/wrapper? This package consists of typings for the guilded.gg API compiled together by the community. No need to write your own typings and reinvent the wheel.
* `js/webhook-client` (**[GitHub](https://github.com/lnfernal/guilded.js/tree/main/packages/webhook-client#readme), [NPM](https://www.npmjs.com/package/js/webhook-client)**) - Library-agnostic webhook client for interaction with guilded.gg API webhooks.
* `js/embeds` (**[GitHub](https://github.com/lnfernal/guilded.js/tree/main/packages/embeds#readme), [NPM](https://www.npmjs.com/package/js/embeds)**) - Library-agnostic embed builder for sending messages with rich content through the guilded.gg API.
* `js/common` (**[GitHub](https://github.com/lnfernal/guilded.js/tree/main/packages/common#readme), [NPM](https://www.npmjs.com/package/js/common)**) - Utilities and structures shared across various js packages.
* `js/itami` (**[GitHub](https://github.com/lnfernal/guilded.js/tree/main/packages/itami#readme)**) - official framework for js/guilded.js, comes with highly customizable commands, listeners, and other abstractions.

## 📥 Installation

<a href="https://npmjs.org/package/guilded"><img src="https://nodei.co/npm/guilded.png" alt="NPM"></a>

**Recommended that you use node v12+**
- `npm install guilded`  
- `yarn add guilded`

## ⚡ Usage
You can find extra examples [here](https://github.com/lnfernal/guilded.js/tree/main/examples)

```ts
const { Client } = require("guilded");

/*
 * ES6:
 * import { Client } from "guilded";
 */

const client = new Client();

client.on('ready', () => console.log(`Bot is successfully logged in`));

client.on("messageCreate", message => {
    if(message.content === "poggers") {
        return message.channel.send("poggers indeed");
    }
})

client.login({
    email: "email",
    password: "password"
});
```

## 📃 Documentation
Documentation is viewable here: https://guilded.js.org

<!--END GETTING STARTED-->

## ✋ Contributing

Contributions are what make the open source community such an amazing place to learn, inspire, and create. Any contributions you make are **greatly appreciated**.

**Please run `npm run bootstrap` after running npm install in your local environment.**
**Please ensure your commits pass the test, lint, and build scripts.**

**We make use of [lerna](https://lerna.js.org/) to manage our monorepo. The main commands used are below**
* `lerna add <module> [--scope=package-name]` - add npm module dependency to all/specific package(s)
* `lerna create <package>` - create a new package
* `npm run bootstrap` = `lerna bootstrap` - recursively install dependencies in all packages and symlink local packages
* `lerna run <npm-script>` - recursively execute command in all packages (must exist in each packages package.json)

## 🤝 Acknowledgements
[Discord.js](https://github.com/discordjs/discord.js) - Main inspiration & lots of derived work.

## ⚖️ LICENSING  
> **Guilded.JS** © [lnfernal](https://github.com/lnfernal), Released under the [MIT](https://github.com/lnfernal/guilded.js/blob/main/LICENSE) License. All subpackages are also released under the MIT License
