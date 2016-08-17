# saihubot
client side chatbot that can be embedded in any web site

Check [Online Demo](https://gasolin.github.io/saihubot/)

## Features

* Chat bot works in your browser without setup a server, which won't send private message elsewhere.
* Tiny size (80 lines that contain the core with 3 plugins in init version) that easy to understand and suit for embed in any web site
* Structure is inspired by [hubot](https://github.com/github/hubot/), which is a server side chatbot framework
  * Provide plugin architecture that able to expand functions
  * Regex based message matching
  * Plugin callbacks are extremely flexible, you can control in-page elements, execute local command, fetch remote data, trigger remote actions...
  * can extend bot functionality by import addons


## How to Install

### Method 1

If you just want to try how the bot looks like, Check [Online Demo](https://gasolin.github.io/saihubot/)

### Method 2

If you want to modify it locally, clone the project, then drag index.html to your browser, now you have a working bot!

### Method 3

If you want embed bot into your web site, clone the project then include the `saihubot.js` in your html file with 2 extra tags:

```html
<div id="history"></div>
<input id="message"><button id="send">Send</button>
<script defer src="saihubot.js"></script>
<script defer src="saihubot-diagnostics.js"></script>
```

## Usage

Saihubot provide 3 default plugins `ping`, `time`, `echo` that you can include via:

```html
<script defer src="saihubot-diagnostics.js"></script>
```

### Ping plugin

```
me: ping
bot: PONG
```

### Time plugin:

```
me: time
bot: Device time is Fri Aug 05 2016 21:22:11 GMT+0800 (CST)
```

### Echo plugin:

```
me: echo Hello World!
bot: Hello World!
```

![Imgur](http://i.imgur.com/Ljjf0Fw.png)

## Developer

### Make an plugin

Plugin denotes rules and responses that the bot use to match and respond to the user.

Open browser's devtool and you can start manipulate `Saihubot` object.
Plugins are located in `Saihubot.responses`, and that is the place all you need to deal with.

Check [Plugin Demo](https://gasolin.github.io/saihubot/plugin) for example.

![Imgur](http://i.imgur.com/mbhTwf6.png)

### Make an addon

Addon denotes extra function that can expand Saihubot's functionality.

You can extend Saihubot's functionality by import extra `saihubot-[addonName].js`:

```js
document.addEventListener('DOMContentLoaded', function() {
  Saihubot.prototype.addonName = {
    ...
  };
});
```

then include the js file after `saihubot.js`.

```html
...
<script defer src="saihubot.js"></script>
<script defer src="saihubot-addonName.js"></script>
```

Check [Addon Demo](https://gasolin.github.io/saihubot/addon) for example.

![Imgur](http://i.imgur.com/qYCES6M.png)

## License

Saihubot use MIT License

## ChangeLog

* 0.2 2016/8/6 change to robot.send method in plugin, add plugin and addon examples
* 0.1 2016/8/5 init version
