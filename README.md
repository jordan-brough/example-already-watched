NOTE: See [master branch](https://github.com/jordan-brough/example-already-watched/blob/master/README.md)
for repro with spring-watcher-listen gem.

Repro **without `spring-watcher-listen` gem**:

```
$ spring stop && rails console
Running via Spring preloader in process 23849
Loading development environment (Rails 6.0.0.rc1)
001 > reload!
Reloading...
=> true
002 >         ** ERROR: directory is already being watched! **

        Directory: /Users/jordan/repos/example-already-watched/node_modules/.bin/compression-webpack-plugin

        is already being watched through: /Users/jordan/repos/example-already-watched/node_modules/compression-webpack-plugin

        MORE INFO: https://github.com/guard/listen/wiki/Duplicate-directory-errors
        ** ERROR: directory is already being watched! **

        Directory: /Users/jordan/repos/example-already-watched/node_modules/@rails/webpacker/node_modules/.bin/compression-webpack-plugin

        is already being watched through: /Users/jordan/repos/example-already-watched/node_modules/compression-webpack-plugin

        MORE INFO: https://github.com/guard/listen/wiki/Duplicate-directory-errors
```
