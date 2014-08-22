Opinsys-documentation
=====================

Opinsys system documentation

### Setup

* Install Jekyll and other gems
```
sudo gem install jekyll nokogiri stylus
```

* *Alternatively* one can install to home directory with:
```
gem install --user-install jekyll nokogiri stylus
```

* but do also set PATH in your shell like gem suggests you to!

* Clone git repo

```
git clone git@github.com:opinsys/opinsys-documentation.git
```

* Go to opinsys-documentation folder and type

```bash
  npm install
```

### Site development

* Start Jekyll

```bash
  jekyll serve --watch
```
* if you are running Jekyll on your local computer, open http://0.0.0.0:4000/opinsys-documentation/
* if you are using Opinsys dev-server, open SERVER_IP:4000/opinsys-documentation/

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
date:   2014-08-22
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
```bash
_posts/kayttoliittyma-ja-perustoiminnot/2014-06-11-ohjelmien-kaynnistaminen.markdown
```

* Locale-files are in
```bash
locales/
```

#### Site images and videos
* are located in assets/images
  * there's two versions of every image
    * image-name.png
    * image-name-small.png

* use this structure when you add new images to any page
```
<div class="pure-u-11-24 images">
<ul>
  <li>
    <a href="{{ site.baseurl }}/assets/images/valitse-menu.png" title="1. Napsauta Menu" class="swipebox">
      <img src="{{ site.baseurl }}/assets/images/valitse-menu-small.png" alt="1. Napsauta Menu">
    </a>
  </li>
  <li>
    <a href="{{ site.baseurl }}/assets/images/menu-poistu-aktiivinen.png" class="swipebox" title="2. Napsauta Poistu">
      <img src="{{ site.baseurl }}/assets/images/menu-poistu-aktiivinen-small.png" alt="2. Napsauta Poistu">
      </a>
  </li>
</ul>
</div>
```
* use this structure when you add new youtube/vimeo -videos to any page
```
<i class="icon-video"></i> <a class="swipebox-video" href="http://www.youtube.com/watch?v=c0BJZy7sXlA">Salasanan vaihto-ohjevideo</a>
```

#### Styles (.styl)
* are located in assets/styles

### Build site and add changes to Git
* When you have done your changes to the site files you need to build the site and add + commit those changes to git
* Stop jekyll server with ctrl + c
* Build the site

```bash
jekyll build
```
* Do git stuff but don't add _site/ at this point

```bash
git add FOLDER/FILENAME(S)
git commit -m "YOUR COMMIT MESSAGE"
git push origin master
```
#### Publish site to gh-pages
* Add _site to git and push it to the gh-pages branch

```bash
git add _site && git commit -m "YOUR COMMIT MESSAGE"
git subtree push --prefix _site origin gh-pages
```

### This site uses
* [jekyl-lunr-js-search](https://github.com/slashdotdash/jekyll-lunr-js-search)
* [swipebox](https://github.com/brutaldesign/swipebox)
* [l20n](http://l20n.org/)
