# Saihubot [![NPM version][npm-image]][npm-url] 
:robot: Framework to build :speech_balloon: message/chat bots in the :globe_with_meridians: **Browser**.
You can add new skills to bot via plugins and extend its ability via addons. All with plain javascript. :clap:

Saihubot's API is very similar to [hubot](https://github.com/github/hubot/)'s API, so developer who have learned hubot-plugins could learn saihu-plugins very quickly. :zap:

Check [Online Demo](https://gasolin.github.io/saihubot/)

## Features

* Chat bot works in your browser, without server setup.
* Written in plain Javascript, compatible with most browsers
* Structure is inspired by [hubot](https://github.com/github/hubot/)
  * Regex based message matching
  * Could write adapter to fully cooperate with your web UI
  * Could swap brain to support different backends
  * Provide plugin architecture that able to expand functions
  * Can extend bot functionality by import addons
* Tiny size, easy to learn (the init version has just 80 lines that bundle with 3 plugins)
* Each message can be customized with any HTML elements
* Reference chat UI style is included
* Plugin callbacks are extremely flexible, you can control in-page elements, execute local command, fetch remote data, trigger remote actions...

## How to use

### Try Saihubot samples online

If you just want to try how the saihubot looks like, Check [Online Demo](https://gasolin.github.io/saihubot/)

### Try Saihubot on github

Fork the project, edit index.html with github editor, save it and see the result on https://[yourname].github.io/saihubot

### Try Saihubot locally

Clone the project with command

```
git clone https://github.com/gasolin/saihubot.git
```

Then drag `samples/index.html` to your browser, now you have a working bot!

### Bootstrap Saihubot

Clone the project then include the `saihubot.js` in your html file with a div tag for message history and the input field:

```html
<body>
  <div id="history"></div>
  <input id="message"><button id="send">Send</button>
  <script>
    document.addEventListener('DOMContentLoaded', function() {
      new SaihuBot({adapter: basicAdapter});
    });
  </script>
</body>
```

The script is used to bootstrap the Saihubot.

```js
new SaihuBot({});
```

Wrap that script in `DOMContentLoaded` event to make sure contents are loaded before running scripts.

You can pass some parameters into it to quickly customize the bot.

And don't forget to include related libraries in the header

```html
<head>
  <script src="saihubot.js"></script>
  <script src="adapters/saihubot-adapter-basic.js"></script>
  <script src="plugins/saihubot-diagnostics.js"></script>
</header>
```

## Usage

Saihubot provide 3 default plugins `ping`, `time`, `echo` that you can include via:

```html
<script src="plugins/saihubot-diagnostics.js"></script>
```

### Ping plugin

```
me: ping
bot: PONG
```

### :clock2: Time plugin:

```
me: time
bot: Device time is Fri Aug 05 2016 21:22:11 GMT+0800 (CST)
```

### :loudspeaker: Echo plugin:

```
me: echo Hello World!
bot: Hello World!
```

![Imgur](http://i.imgur.com/Ljjf0Fwl.png)


Saihubot also provide Search plugins, you can include it via:

```html
<script src="plugins/saihubot-search.js"></script>
```

Check the [Search Demo](https://gasolin.github.io/saihubot/samples/search).

### :mag_right: Google Search plugin:

```
me: g saihubot
bot: Search saihubot via Google
me: google saihubot
bot: Search saihubot via Google
me: search saihubot
bot: Search saihubot via Google
```

### Wikipedia plugin:

```
me: wiki saihubot
bot: Search saihubot via Wikipedia
me: wikipedia saihubot
bot: Search saihubot via Wikipedia
```

### Google Translate plugin

```
me: translate hello
bot: Translate hello via Google Translate
me: tr saihubot
bot: Translate hello via Google Translate
```

## Want to learn more?

Check the [docs](https://github.com/gasolin/saihubot/tree/gh-pages/docs) section.

## What Saihu means?

Saihu(`師傅`) means `master` in Taiwanese, which people used to call the artisans.
Saihubot's origin goal is provide a code sample that make learning [hubot](https://github.com/github/hubot/) and its ES6 variant [Webbybot](https://github.com/gasolin/webbybot/) easier, then I found Saihu is a great way to embed bot into anywhere browser can live with.

## License

Saihubot use MIT License

## ChangeLog

* 0.9 2017/2/18 make index.html as a full feature showcase, dialog with button selection, help plugin with description
* 0.8 2017/2/3 add swappable brain, provide `saihubot-brain-localforage` plugin with [sample](http://gasolin.idv.tw/saihubot/samples/brain.html)
* 0.7 2017/1/27 add reference chat UI style and make sure the last message always scroll into view
* 0.6 2017/1/26 provide run, close, send, render function by swappable adapter
* 0.5 2017/1/25 structured plugins and demo pages, support config, changed catchAll API and support multiple `no command found` responses
* 0.4 2016/8/24 return matched result for message instead of the origin string, add google analytics, add search plugin
* 0.3 2016/8/17 rename from HuohuBot to Saihubot, turn Saihubot to constructor, separate saihubot-dialog.js from addon
* 0.2 2016/8/6 change to robot.send method in plugin, add plugin and addon examples
* 0.1 2016/8/5 init version

[npm-image]: https://badge.fury.io/js/saihubot.svg
[npm-url]: https://npmjs.org/package/saihubot
