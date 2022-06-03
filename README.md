## What is probot-taxes ?

[![npm version](https://badge.fury.io/js/probot-taxes.svg)](https://npmjs.org/package/probot-taxes)  [![downloads](https://img.shields.io/npm/dw/probot-taxes.svg)](https://npmjs.org/package/probot-taxes)  [![open issues](https://img.shields.io/github/issues-raw/dbartholomae/probot-taxes.svg)](https://github.com/dbartholomae/probot-taxes/issues)  [![license](https://img.shields.io/github/license/dbartholomae/probot-taxes.svg)](https://github.com/dbartholomae/probot-taxes/blob/master/LICENSE)

## Installation
```
npm install probot-taxes
```

## Usage
Discord.js v13 Example :
```js
let Taxes = require('probot-taxes')

client.on('messageCreate', message => {
    if (!message.guild) return;
    if (message.author.bot) return;
    if (message.content.toLowerCase.startsWith('tax')) {
    let amount = message.content.split(' ')[1]
    if (isNaN(amount)) return message.reply({content: `Amount should be a number .`})
    let Tax = Taxes(Number(amount))
    let embed = new Discord.MessageEmbed()
    .setTitle('Probot Tax')
    .addField(`Difference`, `${Tax.difference}`)
    .addField(`Tax`, `${Tax.tax}`)
    .addField(`Wasit (Middleman)`, `${Tax.wasit}`)
    message.reply({embeds: [embed]})
    }
})
```
## Opject
```js
let Taxes = require('probot-taxes')
console.log(Taxes('50k'))
//=> { difference: 2632, tax: 52632, wasit: 55403}
```
## Links
[Support Server](https://discord.gg/holy-s)
