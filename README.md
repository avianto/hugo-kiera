# Kiera Theme for Hugo

## Installation

```bash
cd themes
git clone ... kiera
```
Using ```git submodule``` is recommended instead of ```git clone```.

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

```TOML```

```toml
menu = "main"
meta = "false"
```

```YAML```

```yml
menu: "main"
meta: "false"
```


