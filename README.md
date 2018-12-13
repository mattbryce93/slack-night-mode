# Slack Night Mode
A user style for easy Slack theming. [CC0](http://creativecommons.org/publicdomain/zero/1.0/).

## Usage

### Browser

This theme requires that you use [a user styles extension](https://github.com/openstyles/stylus/wiki/Stylish-Alternatives) for your browser, such as Stylus (available for [Firefox](https://addons.mozilla.org/en-US/firefox/addon/styl-us/), [Chrome](https://chrome.google.com/webstore/detail/stylus/clngdbkpkpeebahjckkjfobafhncgmne), and [Opera](https://addons.opera.com/en/extensions/details/stylus/)).

### Desktop App

No official support. Workarounds exist.

**🛑 READ FIRST:** Most workarounds will request the compiled CSS file from this repository. You are strongly discouraged from using a remote CSS file. It's recommended that you create your own copy. An XSS attack could put your Slack client at risk.

[![Chat on Gitter](https://badges.gitter.im/laCour/slack-night-mode.png)](https://gitter.im/slack-night-mode/Lobby?utm_source=share-link&utm_medium=link&utm_campaign=share-link) ([previous discussion](https://github.com/laCour/slack-night-mode/issues/73#issuecomment-242707078))

## Themes

### Supported

#### Black ([source](scss/main.scss) - [build](css/black.css) - [install](https://userstyles.org/styles/117475/slack-night-mode-black))

The primary supported theme. This is an excellent theme if you use a program like f.lux or redshift.

![Black Screenshot](https://userstyles.org/style_screenshots/117475_after.png)

#### Aubergine ([source](scss/themes/_aubergine.scss) - [build](css/variants/aubergine.css) - [install](https://userstyles.org/styles/101971/slack-night-mode))

This is based on Slack's aubergine/maroon style. It's the original theme.

![Aubergine Screenshot](https://userstyles.org/style_screenshots/101971_after.png)

### Variants

* **Arc ([source](scss/themes/_arc-dark.scss) - [build](css/variants/arc-dark.css))** _by [@Lemmmy](https://github.com/Lemmmy)_
* **Midnight Blue ([source](scss/themes/_midnight-blue.scss) - [build](css/variants/midnight-blue.css))** _by [@matt-h](https://github.com/matt-h)_
* **Tomorrow Dark (base16) ([repository](https://github.com/danarnold/slack-night-mode))** _by [@danarnold](https://github.com/danarnold)_

### Extensions

Variants can have extensions which add additional changes.

#### Monospaced ([source](scss/themes/_monospaced.scss))

Replaces the messaging font stack with a monospace font stack.

### Desktop application

To change to dark mode on the Slack Desktop applition, edit the following files:\n
Linux: /usr/lib/slack/resources/app.asar.unpacked/src/static/ssb-interop.js\n
Windows: C:/Program_Files(x64)/slack/resources/app.asar.unpacked/src/static/ssb-interop.js\n

With the following code:

```
document.addEventListener('DOMContentLoaded', function() {
 $.ajax({
   url: 'https://raw.githubusercontent.com/laCour/slack-night-mode/master/css/raw/black.css',
   success: function(css) {
     $("<style></style>").appendTo('head').html(css);
   }
 });
});
```

In order to get the sidebar theme looking consistent I use the following sidebar colour settings:\n
'#333333,#222222,#0074A2,#FFFFFF,#111111,#FFFFFF,#7AD03A,#D54E21'
