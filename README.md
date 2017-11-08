# Kiera Theme for Hugo

Kiera is the theme specialized for presenting writing layout like long essay or technical writing.

## Main Features

* 4 image placements with ```figure``` support using shortcodes.
* Excellent code highlight support thanks to Hugo Chroma.

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

Add regular non-posts related page to main menu add these lines to the page front matter:

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

## Categories & Tags

Both can be used, also can use only one of them or neither.


