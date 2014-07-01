Opinsys-documentation
=====================

Opinsys system documentation

### Work in progress...

### File structure
* Main categories have their own index.html files under named folders
  * For example folder: kayttoliittyma-ja-perustoiminnot have index.html-file
* Each main category have "child"-pages under _posts-folder in named folders
  * For example: _posts/kayttoliittyma-ja-perustoiminnot have all related files to that category

### Local development
```bash
  jekyll serve --watch --baseurl ''
```
* and then open http://0.0.0.0:4000/
* more about [Jekyll basic usage](http://jekyllrb.com/docs/usage/)

### Publish site to gh-pages
* Edit/add/remove files while local development mode. When you are done:

```bash
jekyll build
git add _site && git commit -m "YOUR COMMIT MESSAGE"
git subtree push --prefix _site origin gh-pages
```

### Uses
* [jekyl-lunr-js-search](https://github.com/slashdotdash/jekyll-lunr-js-search)
* [swipebox](https://github.com/brutaldesign/swipebox)
* [l20n](http://l20n.org/)