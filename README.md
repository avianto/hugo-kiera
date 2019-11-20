# 1. Kiera Theme for Hugo

Kiera is the theme specialized in presenting writing layout like long essay or technical writing.

It was originally developed by [b. avianto](https://github.com/avianto/hugo-kiera) and now maintained by [funkydan2](//github.com/funkydan2/)

- [1. Kiera Theme for Hugo](#1-kiera-theme-for-hugo)
  - [1.1. Main Features](#11-main-features)
  - [1.2. Demo](#12-demo)
  - [1.3. Installation](#13-installation)
  - [1.4. Update the theme](#14-update-the-theme)
    - [1.4.1. git submodule method](#141-git-submodule-method)
    - [1.4.2. independent directory method](#142-independent-directory-method)
  - [1.5. Configuration](#15-configuration)
    - [1.5.1. Main Menu](#151-main-menu)
    - [1.5.2. Categories & Tags](#152-categories--tags)
    - [1.5.3. Images](#153-images)
    - [1.5.4. Code highlight](#154-code-highlight)
    - [1.5.5. Font Awesome icons](#155-font-awesome-icons)
    - [1.5.6. Disqus on demand](#156-disqus-on-demand)
    - [1.5.7. Support and Pull Requests](#157-support-and-pull-requests)
  - [1.6. TO DO](#16-to-do)

## 1.1. Main Features

- 4 image placements with `figure` support using shortcodes.
- Excellent code highlight support thanks to Hugo Chroma.
- Use Font Awesome for icons (Cloudflare CDN)
- Utilize normalize.css for consistent styling (Cloudflare CDN)
- Use Google Fonts: Ruda (serif) and Roboto Slab (sans-serif)
- Disqus comment loaded on demand

## 1.2. Demo

Live demo: [https://themes.gohugo.io/theme/hugo-kiera/](https://themes.gohugo.io/theme/hugo-kiera/)

## 1.3. Installation

Change into Hugo directory then:

```console
$ cd themes
$ git clone https://github.com/funkydan2/hugo-kiera.git kiera
```

More detailed instruction at [Hugo Docs](https://gohugo.io/getting-started/).

Using `git submodule` is recommended instead of `git clone` as per recommendation from [Netlify](https://gohugo.io/hosting-and-deployment/hosting-on-netlify/#use-hugo-themes-with-netlify).

```console
$ cd themes
$ git submodule add https://github.com/funkydan2/hugo-kiera.git kiera
```

## 1.4. Update the theme

### 1.4.1. git submodule method

Use `git` to merge latest commits into your project by running:

```bash
$ cd /path/to/the/root/of/your/project/
$ git submodule update --rebase --remote`
```

### 1.4.2. independent directory method

Delete the directory corresponding to the theme and download the latest version of the theme by cloning the repo:

```bash
$ cd /path/to/the/root/of/your/project/
$ rm -rf themes/hugo-kiera/
$ git clone https://github.com/funkydan2/hugo-kiera.git themes/hugo-kiera/
```

## 1.5. Configuration

For reference look inside folder `exampleSite` for content example and `config.toml`.

*Important*: don't delete or move `archetypes` folder from root unless it is necessary. Current Hugo priority lookup will look into this folder first before any other `archetypes` folder and could cause problem.

Recommended optional `config.toml`:

```toml
pygmentsCodeFences = true

disqusShortname = "" #Disqus shortname
googleAnalytics = "" #Google Analytics ID

[author]
    name = ""       #Author name
    github = ""     #Github username
    gitlab = ""     #Gitlab username
    linkedin = ""   #LinkedIn username
    facebook = ""   #Facebook username
    twitter = ""    #Twitter username
    instagram = ""  #Instagram username

[params]
    tagline = "the tagline for this website"
    customCSS = []  #Optional Customised CSS
```

### 1.5.1. Main Menu

Add regular non-posts related page (eq. About page) to the main menu by adding these lines to the page front matter:

TOML:

```toml
menu = "main"
meta = "false"
```

YAML:

```yml
menu: "main"
meta: "false"
```

`meta` refers to time, categories, tags and reading time which are not necessary for this kind of page.

For posts listing page, add `_index.md` file inside `content\posts` folder with these front matter:

TOML:

```toml
+++
title = "Posts"
menu = "main"
weight = "10"
+++
```

### 1.5.2. Categories & Tags

Pages can include both, either, or neither *Categories* or *Tags*.

### 1.5.3. Images

Kiera supports adding image as `img` tag with standard Markdown:

`![Image Title](link/to/image)`

to wrap it with `figure` use:

`{{< figure src="/link/to/image" >}}`

The basic placement is 100% width within content and scaled accordingly in smaller screen. Recommended width for image is 600 pixels minimum.

Kiera supports different placement by adding:

- For `img`, use `![Image Title](link/to/image#placement)`
- For `figure`, use `{{< figure src="/link/to/image" class="placement" >}}`

There are 4 configured placements

- `#full` or `class="full"` for full width.
![full](images/screenshots/full-image.png)
- `#mid` or `class="mid"` for middle:
![float-mid](images/screenshots/mid.png)
- `#float` or `class="float"` for float left:
![float-left](images/screenshots/float-left.png)
- `#float-right` or `class="float-right"` for float right:
![float-right](images/screenshots/float-right.png)

### 1.5.4. Code highlight

Using fenced code with Chroma support.

### 1.5.5. Font Awesome icons

For usage, refer to [Font Awesome](https://fontawesome.com/).

### 1.5.6. Disqus on demand

[Disqus](https://disqus.com/) comments are loaded on demand, by clicking the <kbd>View Comments</kbd> button.

### 1.5.7. Support and Pull Requests

Please use GitHub issues to file bugs. If you can help fixing bugs, optimize the theme or adding features, please do pull requests, I really love to see what others can come up with.

## 1.6. TO DO

- `/layout/_default/terms.html` needs some works, it functions now, barely.
- Adding some user-oriented behavior using JavaScripts.
- Lazyload images.
- i18n support.
