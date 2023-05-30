# Package
dotnet add package System.Data.SqlClient
dotnet add package Microsoft.EntityFrameworkCore
dotnet add package Microsoft.EntityFrameworkCore.SqlServer
dotnet add package Microsoft.EntityFrameworkCore.Tools
dotnet add package Microsoft.EntityFrameworkCore.Design
dotnet add package Microsoft.Extensions.DependencyInjection
dotnet add package Microsoft.Extensions.Logging.Console

dotnet tool install --global dotnet-ef
dotnet tool install -g Microsoft.Web.LibraryManager.Cli

dotnet add package Microsoft.AspNetCore.Identity
dotnet add package Microsoft.AspNetCore.Identity.EntityFrameworkCore
dotnet add package Microsoft.VisualStudio.Web.CodeGeneration.Design
dotnet add package Microsoft.AspNetCore.Identity.UI
dotnet add package Microsoft.AspNetCore.Authentication
dotnet add package Microsoft.AspNetCore.Http.Abstractions
dotnet add package Microsoft.AspNetCore.Authentication.Cookies
dotnet add package Microsoft.AspNetCore.Authentication.Facebook
dotnet add package Microsoft.AspNetCore.Authentication.Google
dotnet add package Microsoft.AspNetCore.Authentication.JwtBearer
dotnet add package Microsoft.AspNetCore.Authentication.MicrosoftAccount
dotnet add package Microsoft.AspNetCore.Authentication.oAuth
dotnet add package Microsoft.AspNetCore.Authentication.OpenIDConnect
dotnet add package Microsoft.AspNetCore.Authentication.Twitter
dotnet add package Microsoft.CodeAnalysis.CSharp.Workspaces

# IdentityUser

donet aspnet-codegenerator identity -dc mydbcontext


# Scaffold (ConnectionString)
Scaffold-DbContext "Server=DESKTOP-GUQBECH;Database=QLDuAn;integrated security=true; Encrypt=false TrustServerCertificate=true;" Microsoft.EntityFrameworkCore.SqlServer -OutputDir Models

# SCSS
npm install --global gulp-cli

npm install gulp
npm install node-sass postcss sass

npm install gulp-sass gulp-less gulp-concat gulp-cssmin gulp-uglify rimraf gulp-postcss gulp-rename

# Thêm cấu hình của SCSS
## gulpfile.js

var gulp = require('gulp');
var sass = require('gulp-sass');
var cssmin = require("gulp-cssmin");
var postcss = require('gulp-postcss');
var autoprefixer = require('autoprefixer');
var concat = require("gulp-concat");

var paths = {
  scss :"./wwwroot/scss/**/*.scss",
  css  : "./wwwroot/css/",
  minCss : "./wwwroot/css/min/",
  concatCssDest : "./wwwroot/css/site.min.css",


  // js : "./wwwroot/js/**/*.js",
  // minJs : "./wwwroot/js/**/*.min.js",
  // concatJsDest : "./wwwroot/js/site.min.js",
  // concatCssDest : "./wwwroot/css/site.min.css",
};


gulp.task('sass', function(cb) {
  gulp
    .src(paths.scss)
    .pipe(sass())
    .pipe(gulp.dest(paths.css))
    .pipe(cssmin())
    .pipe(gulp.dest(paths.minCss));
  cb();
});

gulp.task(
  'default',
  gulp.series('sass', function(cb) {
    gulp.watch(paths.scss, gulp.series('sass'));
    cb();
  })
);

### Để thi hành tác vụ sass chỉ cần gõ lệnh:
gulp sass