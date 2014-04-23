gulp-prefix
=========

A gulp plugin inspired by [html-prefixer](https://github.com/tivac/node-html-prefixer).

Will prefix relative urls in &lt;link&gt;, &lt;script&gt; and &lt;img&gt; tags

###HTML
```html
<html>
  <head>
    <link href="http://cdnjs.com/some-library.css">
    <link href="css/stylesheets.js">
  </head>
  <body>
    <img src="/images/myImage.jpg"/>
    <script src="//cdnjs.com/some-library.js"></script>
    <script src="js/scripts.js"></script>
  </body>
</html>
```



###Usage
```javascript
var gulp = require('gulp'),
    prefix = require('gulp-prefix');

gulp.task('prefix', function(){
  var context = { 'prefix': "http://mydomain.com/assets" };

  gulp.src('index.html')
    .pipe(prefix( context ))
    .pipe(gulp.dest('build'));
});
```

###Output
```html
<html>
  <head>
    <link href="http://cdnjs.com/some-library.css">
    <link href="http://mydomain.com/assets/css/stylesheets.js">
  </head>
  <body>
    <img src="http://mydomain.com/assets/images/myImage.jpg"/>
    <script src="//cdnjs.com/some-library.js"></script>
    <script src="http://mydomain.com/assets/js/scripts.js"></script>
  </body>
</html>
```

License
----

MIT
    
