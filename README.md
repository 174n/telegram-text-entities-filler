# telegram-text-entities-filler

[![last commit](https://img.shields.io/github/last-commit/Rundik/telegram-text-entities-filler.svg)](https://github.com/Rundik/telegram-text-entities-filler/commits/master)
[![version](https://img.shields.io/npm/v/@rundik/telegram-text-entities-filler.svg)](https://www.npmjs.com/package/@rundik/telegram-text-entities-filler)
![downloads](https://img.shields.io/npm/dm/@rundik/telegram-text-entities-filler.svg)
[![license](https://img.shields.io/npm/l/@rundik/telegram-text-entities-filler.svg)](https://github.com/Rundik/telegram-text-entities-filler/blob/master/license)


Simple library that helps fills text with entities markup. Fork of https://www.npmjs.com/package/telegram-text-entities-filler

## Installation

```
$ npm install @rundik/telegram-text-entities-filler
```
or using `yarn`:
```
$ yarn add @rundik/telegram-text-entities-filler
```

## Example

This bot will respond with the same message, keeping the text markup

```js
const Telegraf = require('telegraf');
const { fillMarkdownEntitiesMarkup } = require('@rundik/telegram-text-entities-filler');

const bot = new Telegraf(process.env.BOT_TOKEN);

bot.on('text', (ctx) =>
  ctx.reply(
    fillMarkdownEntitiesMarkup(ctx.message.text, ctx.message.entities),
    { parse_mode: "MarkdownV2" }
  )
);

bot.launch();
```
