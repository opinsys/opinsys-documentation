Opinsys-documentation
=====================

Opinsys system documentation

### Local development

* Install Jekyll
```
gem install jekyll
```

* Clone git repo

```
git clone git@github.com:opinsys/opinsys-documentation.git
```

* Go to opinsys-documentation folder and type

```bash
  npm install
  jekyll serve --watch --baseurl ''
```
* and then open http://0.0.0.0:4000/
* more about [Jekyll basic usage](http://jekyllrb.com/docs/usage/)

* At the moment we need to use baseurl in _config.yml because site is in http://opinsys.github.io/opinsys-documentation/
```
baseurl: /opinsys-documentation
```
* When site url is ohjeet.opinsys.fi, there's no need for that

### Edit site text-files

#### File structure
* Main categories have their own index.html files under named folders
  * For example folder: kayttoliittyma-ja-perustoiminnot have index.html-file
* Each main category have "child"-pages under _posts-folder in named folders
  * For example: _posts/kayttoliittyma-ja-perustoiminnot have all related text-files to that category

* Each main category index-files have this kind of structure at the beginning
```
---
layout: default
lang: fi
title: Käyttöliittymä ja perustoiminnot
icon: icon-rocket
---
```

* Each child-page have this kind of structure at the beginning
```
---
layout: post
title:  "Käyttäjätunnukset ja -profiili"
date:   2013-10-28 11:31:26
categories: kayttoliittyma-ja-perustoiminnot
parent_page_title: Käyttöliittymä ja perustoiminnot
tags:
  - ohjeet
  - käyttäjätunnus
  - salasana
  - profiili
---
```

* layout determine which basic html-structure file uses
  * layouts are in _layouts-folder
* icon determine which icon is used at the home page
  * icons are in vendor/fontello-opinsys-documentation-folder
* categories determine in which main category child-page belongs
  * 'kayttoliittyma-ja-perustoiminnot'-category means that child page is listed under that 'parent'-page

#### Translations
* Some files have l20n-translates at the moment, for example
```
_posts/kayttoliittyma-ja-perustoiminnot/2014-06-11-ohjelmien-kaynnistaminen.markdown
```

* Locale-files are in
```
locales/
```

#### Site images
* are located in assets/images

#### Styles (.styl)
* are locates in assets/styles

### Publish site to gh-pages
* Edit/add/remove files at your local development enviroment. When you are done:

```bash
jekyll build
git add _site && git commit -m "YOUR COMMIT MESSAGE"
git subtree push --prefix _site origin gh-pages
```

### Uses
* [jekyl-lunr-js-search](https://github.com/slashdotdash/jekyll-lunr-js-search)
* [swipebox](https://github.com/brutaldesign/swipebox)
* [l20n](http://l20n.org/)