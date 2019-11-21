# Thursday, 21 November 2019
* Added support for a [stackoverflow](//stackoverflow.com) icon and link (thanks @alfredocambera).

# Thursday, 7 November 2019
Changed the custom RSS feed so it only includes pages from mainSection. This will mean the feed emulates the content of the front page.

# Monday, 4 November 2019
* Fixed a small bug with displaying metadata. This change (of logic) will make the theme work as expected: if you set `meta = false` in frontmatter, meta data won't be displayed, if you set `meta = true` it will. However, this change may change sites which had worked around the previous bug.
* **NEW** support for opengraph and twitter cards. You can configure the image displayed on either a per-site basis by setting `.Site.Params.images` in the config file, or on a per-page basis in the frontmatter. For more details see [the Hugo Docs](https://gohugo.io/templates/internal/#open-graph)

# Sunday, 3 November 2019
* Added favicon support through `.Site.Params.favicon`
* [Fixed comments icon](https://github.com/funkydan2/hugo-kiera/pull/3) (thanks @tobiaszheller)

# Monday, 23 September 2019
* Custom CSS support through config.toml/yaml/json
* Fixed Customised RSS
* Implemented `partialCached` to decrease build times
* Added CSS Styling for contact form text boxes and buttons.

# Saturday, 21 September 2019
* Moved Fontawesome to use Kits
* Updated README.md
