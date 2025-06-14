# Hyde

Hyde is a brazen two-column [hugo](https://gohugo.io) theme based on the [Jekyll](http://jekyllrb.com) theme of the same name.
It pairs a prominent sidebar with uncomplicated content.

![Hyde screenshot](https://f.cloud.github.com/assets/98681/1831228/42af6c6a-7384-11e3-98fb-e0b923ee0468.png)

**Note: this is a fork I (Brendan Abolivier) made to adapt Hyde to my needs. More info [below](#fork).**

## Contents

- [Installation](#installation)
- [Options](#options)
  - [Sidebar menu](#sidebar-menu)
  - [Sidebar description](#sidebar-description)
  - [Sticky sidebar content](#sticky-sidebar-content)
  - [Themes](#themes)
  - [Reverse layout](#reverse-layout)
  - [Disqus](#disqus)
  - [Google Analytics](#google-analytics)
- [Author](#author)
- [Ported by](#ported-by)
- [License](#license)
- [Fork](#fork)


## Installation

### Quick Start

To give you a running start this installation puts a fully configured [starter repo](https://github.com/forestryio/hyde-hugo-starter) into your Git account and sets it up in a content manager / CMS. 

_[Forestry](https://forestry.io) Starter-Kit:_

[![Import this project into Forestry](https://assets.forestry.io/import-to-forestry.svg)](https://app.forestry.io/quick-start?repo=forestryio/hyde-hugo-starter&provider=github&engine=hugo&version=0.49)

### Standard Installation

To install Hyde as your default theme, first install this repository in the `themes/` directory:

    $ cd themes/
    $ git clone https://github.com/spf13/hyde.git

Second, specify `hyde` as your default theme in the `config.toml` file. Just add the line

    theme = "hyde"

at the top of the file.


## Options

Hyde includes some customizable options, typically applied via classes on the `<body>` element.


### Sidebar menu

Create a list of nav links in the sidebar by assigning "menu=main" in the front matter, like so:

**TOML**
```toml
theme = "hyde"

[Menus]
  main = [
      {Name = "Github", URL = "https://github.com/username/"},
      {Name = "LinkedIn", URL = "https://www.linkedin.com/in/username/"}
  ]
```

**YAML**
```yaml
theme: "hyde"

Menus:
  main:
    - Name: "Github"
      URL: "https://github.com/username/"
    - Name: "LinkedIn"
      URL: "https://www.linkedin.com/in/username/"
```

### Sidebar description
Customise the describe of your page using `description`, like so:

**TOML**
```toml
theme = "hyde"

[params]
  description = "Your custom description"
```

**YAML**
```yaml
theme: "hyde"

params:
  description = "Your custom description"
```


### Sticky sidebar content

By default Hyde ships with a sidebar that affixes it's content to the bottom of the sidebar. You can optionally disabled this by removing the `.sidebar-sticky` class from the sidebar's `.container`. Sidebar content will then normally flow from top to bottom.

```html
<!-- Default sidebar -->
<div class="sidebar">
  <div class="container sidebar-sticky">
    ...
  </div>
</div>

<!-- Modified sidebar -->
<div class="sidebar">
  <div class="container">
    ...
  </div>
</div>
```


### Themes

Hyde ships with eight optional themes based on the [base16 color scheme](https://github.com/chriskempson/base16). Apply a theme to change the color scheme (mostly applies to sidebar and links).

![Hyde in red](https://f.cloud.github.com/assets/98681/1831229/42b0b354-7384-11e3-8462-31b8df193fe5.png)

There are eight themes available at this time.

![Hyde theme classes](https://f.cloud.github.com/assets/98681/1817044/e5b0ec06-6f68-11e3-83d7-acd1942797a1.png)

To use a theme, add the `themeColor` variable under `params`, like so:

**TOML**
```toml
theme = "hyde"

[params]
  themeColor = "theme-base-09"
```

**YAML**
```yaml
theme: "hyde"

params:
  themeColor: "theme-base-09"
```

To create your own theme, look to the Themes section of [included CSS file](https://github.com/poole/hyde/blob/master/public/css/hyde.css). Copy any existing theme (they're only a few lines of CSS), rename it, and change the provided colors.

### Reverse layout

![Hyde with reverse layout](https://f.cloud.github.com/assets/98681/1831230/42b0d3ac-7384-11e3-8d54-2065afd03f9e.png)

To reverse page orientation, add the `layoutReverse` variable under `params`, like so:

**TOML**
```toml
theme = "hyde"

[params]
  layoutReverse = true
```

**YAML**
```yaml
theme: "hyde"

params:
  layoutReverse: true
```

### Disqus

You can optionally enable a comment system powered by Disqus for the posts. Simply add the variable `disqusShortname` to your config file.

**TOML**
```toml
disqusShortname = "spf13"
```

**YAML**
```yaml
disqusShortname : spf13
```

> **Note:** Previous version 1.0 the Disqus shortname had to be defined inside the `[params]` block.


## Google Analytics

Google Analytics can be enabled by assigning your tracking code to the `googleAnalytics` variable in the config file:

**TOML**
```toml
googleAnalytics = "Your tracking code"
```

**YAML**
```yaml
googleAnalytics: Your tracking code
```

## Author
**Mark Otto**
- <https://github.com/mdo>
- <https://twitter.com/mdo>

## Ported By
**Steve Francia**
- <https://github.com/spf13>
- <https://twitter.com/spf13>

## License

Open sourced under the [MIT license](LICENSE.md).

<3

## Fork

This is a fork of the Hyde theme I (Brendan Abolivier) made containing a few changes I made:

* Getting rid of Google Fonts
* Adding [Fork Awesome](https://forkaweso.me/Fork-Awesome/)
* Adding meta tags for social network sharing and kind of SEO
* Adding an `author` key in the `params` section from the configuration file
* Adding special links to the sidebar menu using values from the `params` section in the configuration file
* Replacing the `copyright` key in the `params` section from the configuration file with a `creativeCommons` key, expected to be a Creative Commons license identifier (such as `by`, `by-sa`, etc.)
* Adding a proper RSS feed template including items' descriptions in `<description>` tags, and their contents in `<content:encoded>` tags
* Adding support for posts' thumbnails, by supporting a `thumbnail` key in a post's front matter. Note that this value must not contain the `https://myblog.tld/images` part of the image's URL, which is added automatically before the key's value.

See the [live configuration file](https://github.com/babolivier/brendan.abolivier.bzh/blob/master/config.yaml) for examples on how to use these features.

Note that none of the configuration parameters I added are optional (because I don't need them to be). A live demo is available [on my blog](https://brendan.abolivier.bzh).

Of course, everything I didn't mess with belongs to the Hugo Hyde theme's authors and contributor.
