# Ser-Drephs Blog

This is the source code of my personal blog and other public information about me.

## Features of "no-style-please"

Used Yekyll Style is ["no-style-please" from riggraz](https://github.com/riggraz/no-style-please) with some design modifications.

* Fast (**< 1kb of CSS**, see [Page Speed Insights report](https://raw.githubusercontent.com/riggraz/no-style-please/master/_screenshots/page-speed-insights-report.png) and [Lighthouse report](https://raw.githubusercontent.com/riggraz/no-style-please/master/_screenshots/lighthouse-report.png))
* Responsive
* Content first (typography optimized for maximum readability)
* SEO optimized (uses [Jekyll SEO Tag](https://github.com/jekyll/jekyll-seo-tag))
* RSS feed (uses [Jekyll Feed](https://github.com/jekyll/jekyll-feed))
* Fully compatible with [GitHub Pages](https://pages.github.com/) (see [GitHub Pages installation](#github-pages-installation))

### Usage

You can edit `_config.yml` file to customize your blog. You can change things such as the name of the blog, the author, how dates are formatted, etc. Customizable fields should be straightforward to understand, however `_config.yml` contains some comments to help you understand what each fields does.

For further customization (e.g. layout, CSS) see the [official Jekyll's documentation](https://jekyllrb.com/docs/themes/#overriding-theme-defaults) on customizing gem-based themes.

#### Customize the menu

In order to add/edit/delete entries from the main menu, you have to edit the `menu.yml` file inside `_data` folder. Through that file you can define the structure of the menu. Take a look at the default configuration to get an idea of how it works and read on for a more comprehensive explanation.

The `menu.yml` file accepts the following fields:

- `entries` define a new unordered list that will contain menu entries
- each entry is marked by a `-` at the beginning of the line
- each entry has the following attributes:
    - `title`, which defines the text to render for that menu entry
    - `url`, which can either be a URL or `false`. If it is `false`, the entry will be rendered as plain text; otherwise the entry will be rendered as a link pointing to the specified URL. Note that the URL can either be relative or absolute.
    - `post_list`, which can be `true` or `false`. If it is true, the entry will have all posts in the site as subentries. This is used to render your post list.
    - `entries`, yes, you can have entries inside entries. In this way you can create nested sublists!

### Post Reference

To start a new post use:
```
---
layout: post
title: 'Start of a new blog'
---
```

Or with Slug (permalink):
```
---
layout: post
slug: start of a new blog
---
```

To create a `hr` with text use:
```
---
{: data-content="discussions"}
```

To create a footnote use `[^1]` with (tbe?):
```
---
{: data-content="footnotes"}
[^1]: ...
```


### License

The theme is available as open source under the terms of the [MIT License](https://opensource.org/licenses/MIT).

