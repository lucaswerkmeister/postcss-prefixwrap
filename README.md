
# [PostCSS Prefix Wrap](https://github.com/dbtedman/postcss-prefixwrap)

[![Build Status](https://travis-ci.org/dbtedman/postcss-prefixwrap.svg?branch=master)](https://travis-ci.org/dbtedman/postcss-prefixwrap) [![NPM Version](https://img.shields.io/npm/v/postcss-prefixwrap.svg)](https://www.npmjs.com/package/postcss-prefixwrap)  [![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE.md)

A [PostCSS](http://postcss.org) plugin that is used to wrap css styles with a css selector to constrain their affect on parent elements in a page.

## Where do I start?

> These instructions are only for this plugin, see [PostCSS](http://postcss.org) website for framework information.

1\. Install the plugin.

```bash
npm install --save-dev postcss-prefixwrap
```

2\. Add to your [PostCSS](http://postcss.org) configuration.


```javascript
// Example using Gulp.js, based on https://github.com/postcss/gulp-postcss README.md.

var gulp = require('gulp');
var postcss = require('gulp-postcss');
var prefixwrap = require("postcss-prefixwrap"); // The require for PostCSS Prefix Wrap.

gulp.task("css", function () {
    var processors = [
        prefixwrap(".my-custom-wrap")
    ];
    return gulp.src("./src/*.css")
        .pipe(postcss(processors))
        .pipe(gulp.dest("./dest"));
});
```

3\. Add the container to your markup.

```html
<div class="my-custom-wrap">
<!-- Your existing markup. -->
</div>
```

4\. View your css, now prefix wrapped.

```css
/* Before */

p {
  color: red;
}

body {
  font-size: 16px;
}
```

```css
/* After */

.my-custom-wrap p {
  color: red;
}

.my-custom-wrap {
  font-size: 16px;
}
```

---

Created [Down Under](https://en.wikipedia.org/wiki/Australia) by [Daniel Tedman](https://danieltedman.com) and [Jeff Teng](https://jafoteng.co).

[![Australia](https://danieltedman.com/images/Australia.png)](https://en.wikipedia.org/wiki/Australia)