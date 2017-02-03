---
title: Saihubot
permalink: /docs/index.html
layout: docs
---

## Getting Started With Saihubot

## Developer

### Make an plugin

Plugin denotes rules and responses that the bot use to match and respond to the user.

Open browser's devtool and you can start manipulate `Saihubot` object.
Plugins are located in `Saihubot.responses`, and that is the place all you need to deal with.

Check [Plugin Demo](https://gasolin.github.io/saihubot/samples/plugin) for example.

![Imgur](http://i.imgur.com/mbhTwf6l.png)

### Make an addon

Addon denotes extra function that can expand Saihubot's functionality.

You can extend Saihubot's functionality by import extra `saihubot-addon-[addonName].js`:

```js
Saihubot.prototype.addonName = {
  ...
};
```

then include the js file after `saihubot.js`.

```html
...
<script defer src="saihubot.js"></script>
<script defer src="saihubot-addon-[addonName].js"></script>
```

Check [Addon Demo](https://gasolin.github.io/saihubot/samples/addon) for example.

![Imgur](http://i.imgur.com/qYCES6Ml.png)

### Make an adapter

To embed Saihubot in your existing web site, you can write your own Saihubot adapter.
Saihubot adapter is used to adapt with any web UI.

Check [saihubot-adapter-basic](https://github.com/gasolin/saihubot/tree/gh-pages/adapters/saihubot-adapter-basic.js)
This adapter is cooperate with [index.html](https://github.com/gasolin/saihubot/tree/gh-pages/index.html) and all other [samples](https://github.com/gasolin/saihubot/tree/gh-pages/samples).

### Make a brain

The brain is used to store something generated when user talk with the bot.

[saihubot-brain-localforage.js](https://github.com/gasolin/saihubot/tree/gh-pages/plugins/saihubot-brain-localforage.js) is created to store brain content with browser storage.
You can find [sample](http://gasolin.idv.tw/saihubot/samples/brain.html) here.