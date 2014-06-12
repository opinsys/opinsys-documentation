Opinsys-documentation
=====================

Opinsys system documentation

### Work in progress...

### Local development
```bash
  jekyll serve --watch --baseurl ''
```

### Publish site to gh-pages
Edit/add/remove files while local development mode. When you are done:

```bash
jekyll build
git add _site && git commit -m "YOUR COMMIT MESSAGE"
git subtree push --prefix _site origin gh-pages
```

### Uses
* [jekyl-lunr-js-search](https://github.com/slashdotdash/jekyll-lunr-js-search)
* [swipebox](https://github.com/brutaldesign/swipebox)