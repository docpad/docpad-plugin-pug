# [Pug](http://pugjs.org/) Plugin for [DocPad](http://docpad.org)

<!-- BADGES/ -->

<span class="badge-travisci"><a href="http://travis-ci.org/docpad/docpad-plugin-pug" title="Check this project's build status on TravisCI"><img src="https://img.shields.io/travis/docpad/docpad-plugin-pug/master.svg" alt="Travis CI Build Status" /></a></span>
<span class="badge-npmversion"><a href="https://npmjs.org/package/docpad-plugin-pug" title="View this project on NPM"><img src="https://img.shields.io/npm/v/docpad-plugin-pug.svg" alt="NPM version" /></a></span>
<span class="badge-npmdownloads"><a href="https://npmjs.org/package/docpad-plugin-pug" title="View this project on NPM"><img src="https://img.shields.io/npm/dm/docpad-plugin-pug.svg" alt="NPM downloads" /></a></span>
<span class="badge-daviddm"><a href="https://david-dm.org/docpad/docpad-plugin-pug" title="View the status of this project's dependencies on DavidDM"><img src="https://img.shields.io/david/docpad/docpad-plugin-pug.svg" alt="Dependency Status" /></a></span>
<span class="badge-daviddmdev"><a href="https://david-dm.org/docpad/docpad-plugin-pug#info=devDependencies" title="View the status of this project's development dependencies on DavidDM"><img src="https://img.shields.io/david/dev/docpad/docpad-plugin-pug.svg" alt="Dev Dependency Status" /></a></span>
<br class="badge-separator" />
<span class="badge-slackin"><a href="https://slack.bevry.me" title="Join this project's slack community"><img src="https://slack.bevry.me/badge.svg" alt="Slack community badge" /></a></span>
<span class="badge-patreon"><a href="http://patreon.com/bevry" title="Donate to this project using Patreon"><img src="https://img.shields.io/badge/patreon-donate-yellow.svg" alt="Patreon donate button" /></a></span>
<span class="badge-gratipay"><a href="https://www.gratipay.com/bevry" title="Donate weekly to this project using Gratipay"><img src="https://img.shields.io/badge/gratipay-donate-yellow.svg" alt="Gratipay donate button" /></a></span>
<span class="badge-flattr"><a href="http://flattr.com/thing/344188/balupton-on-Flattr" title="Donate to this project using Flattr"><img src="https://img.shields.io/badge/flattr-donate-yellow.svg" alt="Flattr donate button" /></a></span>
<span class="badge-paypal"><a href="https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&amp;hosted_button_id=QB8GQPZAH84N6" title="Donate to this project using Paypal"><img src="https://img.shields.io/badge/paypal-donate-yellow.svg" alt="PayPal donate button" /></a></span>
<span class="badge-bitcoin"><a href="https://bevry.me/bitcoin" title="Donate once-off to this project using Bitcoin"><img src="https://img.shields.io/badge/bitcoin-donate-yellow.svg" alt="Bitcoin donate button" /></a></span>
<span class="badge-wishlist"><a href="https://bevry.me/wishlist" title="Buy an item on our wishlist for us"><img src="https://img.shields.io/badge/wishlist-donate-yellow.svg" alt="Wishlist browse button" /></a></span>

<!-- /BADGES -->


Adds support for the [Pug](http://pugjs.org/) templating engine to [DocPad](https://docpad.org)

Convention:  `anything.pug`


## Install

```
docpad install pug
```


## Awareness

Before you get started with Pug, it is important to be aware of one thing. The majority of support questions that come through with DocPad, aren't actually DocPad issues, but Pug issues. People confusing the syntax, Pug doing it's own templating magic, things like that.

The DocPad team recommends you try one of the many other [amazing templating engines](http://docpad.org/docs/plugins#renderers) that are available, over trying to use Pug.

If you still insist on using Pug, please be aware, Pug will be a slippery slope, but luckily there are determined Pug users here to help :)


## Usage

``` pug
---
title: "Pug Example"
---

h1= document.title

ul
	each page in getCollection("html").findAll({isPage:true}).toJSON()
		li(class!=page.id === document.id ? 'active' : 'inactive')
			a(href=page.url)
				= page.title
```

### Template Helpers as Filters

Use just like any pug template. However, we do add any docpad template helpers you may have as pug filters. There are two ways you can use these filters:

``` pug
-# first way, calls the template helper like: myTemplateHelper("content", {opt1="blah",opt2="blah",opt3=true})
:myTemplateHelper(opt1=blah,opt2=blah,opt3)
    content

-# second way, calls the template helper like: myTemplateHelper(arg1, arg2)
:myTemplateHelper(args)
    arg1
    arg2
```

NOTE: Not all template helpers support being called this way. If it doesn't work, we'd recommend using the text plugin to render eco which includes your template helper call. See following section.

### Pug :filters

All [JSTransformers](https://www.npmjs.com/browse/keyword/jstransformer) can now be used as pug filters.


### Rendering with the Text Plugin
You can use the [text plugin](http://docpad.org/plugin/text) to render different parts of your template with different markups that are support by your docpad setup. Once installed, you can do things like:

``` pug
:t(render="markdown")
    here is some *markdown*

:t(render="html.md.eco")
    here is some <%-'eco'.toUpperCase()%> to *markdown* to html

:t(render="html.eco")
    my url is <%-@document.url%>
```


<!-- HISTORY/ -->

<h2>History</h2>

<a href="https://github.com/docpad/docpad-plugin-pug/blob/master/HISTORY.md#files">Discover the release history by heading on over to the <code>HISTORY.md</code> file.</a>

<!-- /HISTORY -->


<!-- CONTRIBUTE/ -->

<h2>Contribute</h2>

<a href="https://github.com/docpad/docpad-plugin-pug/blob/master/CONTRIBUTING.md#files">Discover how you can contribute by heading on over to the <code>CONTRIBUTING.md</code> file.</a>

<!-- /CONTRIBUTE -->


<!-- BACKERS/ -->

<h2>Backers</h2>

<h3>Maintainers</h3>

These amazing people are maintaining this project:

<ul><li><a href="http://balupton.com">Benjamin Lupton</a> — <a href="https://github.com/docpad/docpad-plugin-pug/commits?author=balupton" title="View the GitHub contributions of Benjamin Lupton on repository docpad/docpad-plugin-pug">view contributions</a></li></ul>

<h3>Sponsors</h3>

No sponsors yet! Will you be the first?

<span class="badge-patreon"><a href="http://patreon.com/bevry" title="Donate to this project using Patreon"><img src="https://img.shields.io/badge/patreon-donate-yellow.svg" alt="Patreon donate button" /></a></span>
<span class="badge-gratipay"><a href="https://www.gratipay.com/bevry" title="Donate weekly to this project using Gratipay"><img src="https://img.shields.io/badge/gratipay-donate-yellow.svg" alt="Gratipay donate button" /></a></span>
<span class="badge-flattr"><a href="http://flattr.com/thing/344188/balupton-on-Flattr" title="Donate to this project using Flattr"><img src="https://img.shields.io/badge/flattr-donate-yellow.svg" alt="Flattr donate button" /></a></span>
<span class="badge-paypal"><a href="https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&amp;hosted_button_id=QB8GQPZAH84N6" title="Donate to this project using Paypal"><img src="https://img.shields.io/badge/paypal-donate-yellow.svg" alt="PayPal donate button" /></a></span>
<span class="badge-bitcoin"><a href="https://bevry.me/bitcoin" title="Donate once-off to this project using Bitcoin"><img src="https://img.shields.io/badge/bitcoin-donate-yellow.svg" alt="Bitcoin donate button" /></a></span>
<span class="badge-wishlist"><a href="https://bevry.me/wishlist" title="Buy an item on our wishlist for us"><img src="https://img.shields.io/badge/wishlist-donate-yellow.svg" alt="Wishlist browse button" /></a></span>

<h3>Contributors</h3>

These amazing people have contributed code to this project:

<ul><li><a href="http://balupton.com">Benjamin Lupton</a> — <a href="https://github.com/docpad/docpad-plugin-pug/commits?author=balupton" title="View the GitHub contributions of Benjamin Lupton on repository docpad/docpad-plugin-pug">view contributions</a></li>
<li><a href="http://phaseone.me">Evan Bovie</a> — <a href="https://github.com/docpad/docpad-plugin-pug/commits?author=phaseOne" title="View the GitHub contributions of Evan Bovie on repository docpad/docpad-plugin-pug">view contributions</a></li>
<li><a href="http://kizu.ru/en/">Roman Komarov</a> — <a href="https://github.com/docpad/docpad-plugin-pug/commits?author=kizu" title="View the GitHub contributions of Roman Komarov on repository docpad/docpad-plugin-pug">view contributions</a></li>
<li><a href="https://github.com/toabi">Tobias Birmili</a> — <a href="https://github.com/docpad/docpad-plugin-pug/commits?author=toabi" title="View the GitHub contributions of Tobias Birmili on repository docpad/docpad-plugin-pug">view contributions</a></li>
<li><a href="https://github.com/darrrk">Vladislav Botvin</a> — <a href="https://github.com/docpad/docpad-plugin-pug/commits?author=darrrk" title="View the GitHub contributions of Vladislav Botvin on repository docpad/docpad-plugin-pug">view contributions</a></li>
<li><a href="pitak.net">Roman Piták</a> — <a href="https://github.com/docpad/docpad-plugin-pug/commits?author=romanpitak" title="View the GitHub contributions of Roman Piták on repository docpad/docpad-plugin-pug">view contributions</a></li>
<li><a href="craigmdennis.com">Craig Dennis</a> — <a href="https://github.com/docpad/docpad-plugin-pug/commits?author=craigmdennis" title="View the GitHub contributions of Craig Dennis on repository docpad/docpad-plugin-pug">view contributions</a></li></ul>

<a href="https://github.com/docpad/docpad-plugin-pug/blob/master/CONTRIBUTING.md#files">Discover how you can contribute by heading on over to the <code>CONTRIBUTING.md</code> file.</a>

<!-- /BACKERS -->


<!-- LICENSE/ -->

<h2>License</h2>

Unless stated otherwise all works are:

<ul><li>Copyright &copy; 2012+ <a href="http://bevry.me">Bevry Pty Ltd</a></li>
<li>Copyright &copy; 2011 <a href="http://balupton.com">Benjamin Lupton</a></li></ul>

and licensed under:

<ul><li><a href="http://spdx.org/licenses/MIT.html">MIT License</a></li></ul>

<!-- /LICENSE -->