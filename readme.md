<!-- scss template -->
scss installation steps
  1. npm install --global gulp-cli 
  <!-- package.json -->
  2. npm init 
  <!-- dependancey -->
  3. npm install gulp -D <!-- gulp -->
  4. npm install sass gulp-sass -D <!-- gulp-scss-->
  5. npm install gulp-uglifycss -D <!-- minified -->

  <!-- gulp js file -->
  6. touch gulpfile.js

<!-- paste code into gulpfile.js -->
<!-- Code : -->
var gulp = require('gulp');
const sass = require('gulp-sass')(require('sass'));
var uglifycss = require('gulp-uglifycss');

<!--task scss compile into css -->
gulp.task('scss', function(){
    return gulp.src('./scss/*.scss')
      .pipe(sass().on('error', sass.logError))
      .pipe(gulp.dest('./css'));
});

<!-- task css minified -->
gulp.task('css', function(){
    gulp.src('./css/*.css')
    .pipe(uglifycss({
        "uglyComments": true
    }))
    .pipe(gulp.dest('./dist'));
});

gulp.task('run', gulp.series('scss', 'css'));

gulp.task('watch', function(){
    gulp.watch('./scss/*.scss', ['scss']);
    gulp.watch('./css/*.css', ['css']);
});
<!-- defalt command -->
gulp.task('default', gulp.series('run', 'watch'));

<!-- run command to compile scss -->
run gulp

<!-- files structures  -->
    <!-- converted css file -->
    1. css/style.css 

    <!-- css minified file -->
    2. dist/style.css

    <!-- main js file -->
    3. js/main.js

    <!-- scss files -->
    4. scss/
        _color.scss  <!-- color variabls file -->
        _global.scss <!-- global scss with mixin -->
        _main.scss <!-- custom main scss code -->
        _desktop.scss <!-- desktop -->
        _desktop-min.scss <!-- min desktop -->
        _tabs.scss <!-- tabs -->
        _mobiles.scss <!-- mobile -->
        _variables.scss <!-- breakpoints -->
        style.scss   <!-- main scss file -->

<!-- index file info -->
Header
  1. logo
  2. main menu
  3. login/register
6 blocks
  1. hero banner
  2. Delivering goods
  3. Paste your images in isometric components 
  4. Web system for living
  5. USERS REGISTRED
  6. Download the app now ! (banner)
footer
  1. social icons
  2. links 