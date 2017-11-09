# Kiera Theme for Hugo

Kiera is the theme specialized in presenting writing layout like long essay or technical writing.

## Main Features

* 4 image placements with `figure` support using shortcodes.
* Excellent code highlight support thanks to Hugo Chroma. 
* Use Font Awesome for icons (Cloudflare CDN)
* Utilize normalize.css for consistent styling (Cloudflare CDN)
* Use Google Fonts: Ruda (serif) and Roboto Slab (sans-serif)
* Disqus comment loaded on demand

## Installation 

```console
$ cd themes
$ git clone ... kiera
```

More detailed instruction at [Hugo Docs](http://gohugo.io/themes/installing-and-using-themes/).

Using `git submodule` is recommended instead of `git clone` as per recommendation from [Netlify](https://gohugo.io/hosting-and-deployment/hosting-on-netlify/#use-hugo-themes-with-netlify).

## Configuration

*Important*: delete or move `archetypes` folder from root unless it is necessary. Current Hugo priority lookup will look into this folder first before any other `archetypes` folder and could cause problem.

Optional `config.toml`:

```toml
pygmentsCodeFences = true

disqusShortname = ""
googleAnalytics = ""

[author]
    name = ""
    github = ""
    gitlab = ""
    linkedin = ""
    facebook = ""
    twitter = ""
    instagram = ""

[params]
    tagline = "the tagline for this website"
```

## Main Menu

Add regular non-posts related page (eq. About page) to main menu by adding these lines to the page front matter:

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

```meta``` refers to time, categories, tags and reading time which are not necessary for this kind of page.

For posts listing page, add `_index.md` file inside `content\posts` folder with these front matter:

```toml

+++
title = "Posts"
menu = "main"
weight = "10"
+++

```

## Categories & Tags

Both can be used, also can use only one of them or neither.

## Images

Kiera supports adding image as `img` tag with standard Markdown:

`![Image Title](link/to/image)`

to wrap it with `figure` use:

`{{< figure src="/link/to/image" >}}`

The basic placement is 100% width within content and scaled accordingly in smaller screen. Recommended width for image is 600 pixels minimum.

Kiera supports different placement by adding:

* For `img`, use `![Image Title](link/to/image#placement)`
* For `figure`, use `{{< figure src="/link/to/image" class="placement" >}}`

There are 4 configured placements

* `#full` or `class="full"` for full width.
![](images/screenshots/full-image.png)
* `#mid` or `class="mid"` for middle:
![](images/screenshots/mid.png)
* `#float` or `class="float"` for float left:
![](images/screenshots/float-left.png)
* `#float-right` or `class="float-right"` for float right:
![](images/screenshots/float-right.png)

## Code Hightlight

Using fenced code with Chroma support.

## Font Awesome icons

For usage, refer to [Font Awesome](https://fontawesome.io).

## Disqus On Demand

Disqus comments are loaded on demand, by clicking <kbd>View Comments</kbd> button.

## Support and Pull Requests

Please use GitHub issues to file bugs. If you can help fixing bugs, optimize the theme or adding features, please do pull requests, I really love to see what others can come up with.

## TO DO

* _default/terms.html needs some works.
* 


