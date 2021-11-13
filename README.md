# Kiera Theme for Hugo

Kiera is the theme specialized in presenting writing layout like long essay or technical writing.

It was originally developed by [b. avianto](https://github.com/avianto/hugo-kiera) and now maintained by [funkydan2](//github.com/funkydan2/)

![Screenshot](https://github.com/funkydan2/hugo-kiera/raw/master/images/screenshot.png)

- [Kiera Theme for Hugo](#kiera-theme-for-hugo)
  - [Main Features](#main-features)
  - [Demo](#demo)
  - [Installation](#installation)
  - [Update the theme](#update-the-theme)
    - [git submodule method](#git-submodule-method)
    - [independent directory method](#independent-directory-method)
  - [Configuration](#configuration)
    - [Menus](#menus)
    - [Categories & Tags](#categories--tags)
    - [Images](#images)
    - [Code highlight](#code-highlight)
    - [Font Awesome icons](#font-awesome-icons)
    - [Mathematics](#mathematics)
    - [Commenting](#static-commenting)
  - [Support and Pull Requests](#support-and-pull-requests)

## Main Features
- Simple, 'no-nonsense' styling.
- 4 image placements with `figure` support using shortcodes.
- (Optional) Feature images for posts and twiter cards.
- Excellent code highlight support thanks to Hugo Chroma.
- Use Font Awesome for icons.
- Utilize normalize.css for consistent styling (Cloudflare CDN).
- Use Google Fonts: Ruda (serif) and Roboto Slab (sans-serif).
- [Disqus](https://disqus.com) or [Utterances](https://utteranc.es) comments loaded on demand.
- Supports downloading extra [Google Fonts](https://fonts.google.com/).

## Demo

Live demo: [https://themes.gohugo.io/themes/hugo-kiera/](https://themes.gohugo.io/themes/hugo-kiera/)

## Installation

Change into Hugo directory then:

```console
$ cd themes
$ git clone https://github.com/funkydan2/hugo-kiera.git hugo-kiera
```

More detailed instruction at [Hugo Docs](https://gohugo.io/getting-started/).

Using `git submodule` is recommended instead of `git clone` as per recommendation from [Netlify](https://gohugo.io/hosting-and-deployment/hosting-on-netlify/#use-hugo-themes-with-netlify).

```console
$ cd /path/to/the/root/of/your/project/themes
$ git submodule add https://github.com/funkydan2/hugo-kiera.git
```

## Update the theme

### git submodule method

Use `git` to merge latest commits into your project by running:

```bash
$ cd /path/to/the/root/of/your/project/
$ git submodule update --rebase --remote
```

### independent directory method

Delete the directory corresponding to the theme and download the latest version of the theme by cloning the repo:

```bash
$ cd /path/to/the/root/of/your/project/
$ rm -rf themes/hugo-kiera/
$ git clone https://github.com/funkydan2/hugo-kiera.git themes/hugo-kiera/
```

## Configuration

For reference look inside folder `exampleSite` for content example and `config.toml`.

*Important*: don't delete or move `archetypes` folder from root unless it is necessary. Current Hugo priority lookup will look into this folder first before any other `archetypes` folder and could cause problem.

Recommended optional `config.toml`:

```toml
pygmentsCodeFences = true

disqusShortname = "" #Disqus shortname
googleAnalytics = "" #Google Analytics ID

[author]
    name = ""           #Author name
    github = ""         #Github username
    gitlab = ""         #Gitlab username
    linkedin = ""       #LinkedIn username
    facebook = ""       #Facebook username
    twitter = ""        #Twitter username
    instagram = ""      #Instagram username
    stackoverflow = ""  #StackOverflow username
    devto = ""          #Dev.to username 

[params]
    tagline = "the tagline for this website"
    customCSS = []  #Optional Customised CSS
    disableDarkModeCSS = false # disables css style for users using dark-mode
```

### Menus

To add non-posts related page (eq. About page) to the main menu, adding these lines to the page [front matter](https://gohugo.io/content-management/front-matter/):

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
title = "Posts"
menu = "main"
weight = "10"
```

YAML:

```yml
title : "Posts"
menu : "main"
weight : "10"
```

Following menus are available:

* `main`, displayed in the navigation bar at the top of the page
* `footer`, displayed on the lower right, in the footer 

### Categories & Tags

Pages can include both, either, or neither *Categories* or *Tags*.
To link to tags use the url `/tags/` (e.g. `https://example.com/tags/`) and `/categories/` for categories.

### Images

#### Site header

A side header can be added in `config.toml`.

```
site_logo = "/link/to/image"
```

It is possible to use full width image as well, using either `/link/to/image#full` (which will affect only this image and
not the featured images for posts which may override the site header image) or `site_logo_classes = "full-image"` in `config.toml` (which
will affect all header images, even if a featured image of a post overrides the site logo).

#### Featured images for posts

A featured image for a post which will be shown in list overviews and at the top of the post page can be added in the frontmatter.

```
images: ["/link/to/image"]
```

Here, too, it is possible to display the image in full width appending `#full` or `#float` to the URL (see below).

Featured images can override the site logo on the post page, using `replace_site_logo: false` in the frontmatter.

#### Images in text

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

### Code highlight

Using fenced code with Chroma support.

### Font Awesome icons

For usage, refer to [Font Awesome](https://fontawesome.com/).

### Mathematics

Set `Params.mathjax` to true to enable support of mathematics display using [MathJax](https://mathjax.org/).  Math should be, by default, surrounded by dollar signs and produced using LaTeX syntax.  Options may be overriden using `static/js/mathjax-config.js`.

### Static Commenting

[Disqus](https://disqus.com/) comments are loaded on demand, by clicking the <kbd>View Comments</kbd> button. Disqus comments can be automatically loaded and displayed by setting `CommentAutoload = true` in `config.toml`.

[Utterances](https://utteranc.es), a Git based comment system, is also available. Utterance comments are loaded and displayed by default.

Comments can be disabled for a single page by setting `disableComments = true` in the page frontmatter.

### Last Modified Date

If the `lastmod` option is set on a page/post, either manually or because `enableGitInfo` is set to true, a line including the page's last modification will be shown after the post date.

## Support and Pull Requests

Please use GitHub issues to file bugs. If you can help fixing bugs, optimize the theme or adding features, please do pull requests, I really love to see what others can come up with.
