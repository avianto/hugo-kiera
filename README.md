# Kiera Theme for Hugo

Kiera is the theme specialized for presenting writing layout like long essay or technical writing.

## Main Features

* 4 image placements with ```figure``` support using shortcodes.
* Excellent code highlight support thanks to Hugo Chroma. 
* Use Font Awesome for icons (Cloudflare CDN)
* Utilize normalize.css for consistent styling (Cloudflare CDN)
* Use Google Fonts, Ruda (serif) and Roboto Slab (sans-serif)

## Installation 

```console
cd themes
git clone ... kiera
```
Using ```git submodule``` is recommended instead of ```git clone``` as per recommendation from [Netlify](https://gohugo.io/hosting-and-deployment/hosting-on-netlify/#use-hugo-themes-with-netlify)

## Configuration

Optional ```config.toml```:

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

## Categories & Tags

Both can be used, also can use only one of them or neither.

## Images

Kiera supports adding image as ```img``` tag with standard Markdown

```![Image Title](link/to/image#full)```

or use 

```{{< figure src="/link/to/image" class="full" >}}```

to add it as ```figure```

*Important*: ```#full``` or ```class="full"``` is necessary for image placement. There are 4 placements:

* ```#full``` or ```class="full"``` for full width
![](screenshots/full-image.png)
* ```#mid``` or ```class="mid"``` for middle
![](screenshots/mid.png)
* ```#float``` or ```class="float"``` for float left
![](screenshots/float-left.png)
* ```#float-right``` or ```class="float-right"``` for float right
![](screenshots/float-right.png)

## Code Hightlight




