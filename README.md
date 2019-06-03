NOTE: See the [without-spring-watcher-listen](https://github.com/jordan-brough/example-already-watched/blob/without-spring-watcher-listen/README.md)
branch for a repro that happens even without the `spring-watcher-listen` gem.

Repro:

```
$ sw_vers
ProductName:      Mac OS X
ProductVersion:   10.13.6
BuildVersion:     17G7024
Darwin Kernel Version 17.7.0: Wed Apr 24 21:17:24 PDT 2019; root:xnu-4570.71.45~1/RELEASE_X86_64



$ which ruby
/Users/jordan/.asdf/shims/ruby



$ ruby --version
ruby 2.6.3p62 (2019-04-16 revision 67580) [x86_64-darwin17]



$ rails --version
Rails 6.0.0.rc1



$ rails new example-already-watched
      create  
      create  README.md
      create  Rakefile
      create  .ruby-version
      create  config.ru
      create  .gitignore
      create  Gemfile
         run  git init from "."
Initialized empty Git repository in /private/tmp/example-already-watched/.git/
      create  package.json
      create  app
      create  app/assets/config/manifest.js
      create  app/assets/stylesheets/application.css
      create  app/channels/application_cable/channel.rb
      create  app/channels/application_cable/connection.rb
      create  app/controllers/application_controller.rb
      create  app/helpers/application_helper.rb
      create  app/javascript/channels/consumer.js
      create  app/javascript/channels/index.js
      create  app/javascript/packs/application.js
      create  app/jobs/application_job.rb
      create  app/mailers/application_mailer.rb
      create  app/models/application_record.rb
      create  app/views/layouts/application.html.erb
      create  app/views/layouts/mailer.html.erb
      create  app/views/layouts/mailer.text.erb
      create  app/assets/images/.keep
      create  app/controllers/concerns/.keep
      create  app/models/concerns/.keep
      create  bin
      create  bin/rails
      create  bin/rake
      create  bin/setup
      create  bin/yarn
      create  config
      create  config/routes.rb
      create  config/application.rb
      create  config/environment.rb
      create  config/cable.yml
      create  config/puma.rb
      create  config/spring.rb
      create  config/storage.yml
      create  config/environments
      create  config/environments/development.rb
      create  config/environments/production.rb
      create  config/environments/test.rb
      create  config/initializers
      create  config/initializers/application_controller_renderer.rb
      create  config/initializers/assets.rb
      create  config/initializers/backtrace_silencers.rb
      create  config/initializers/content_security_policy.rb
      create  config/initializers/cookies_serializer.rb
      create  config/initializers/cors.rb
      create  config/initializers/filter_parameter_logging.rb
      create  config/initializers/inflections.rb
      create  config/initializers/mime_types.rb
      create  config/initializers/new_framework_defaults_6_0.rb
      create  config/initializers/wrap_parameters.rb
      create  config/locales
      create  config/locales/en.yml
      create  config/master.key
      append  .gitignore
      create  config/boot.rb
      create  config/database.yml
      create  db
      create  db/seeds.rb
      create  lib
      create  lib/tasks
      create  lib/tasks/.keep
      create  lib/assets
      create  lib/assets/.keep
      create  log
      create  log/.keep
      create  public
      create  public/404.html
      create  public/422.html
      create  public/500.html
      create  public/apple-touch-icon-precomposed.png
      create  public/apple-touch-icon.png
      create  public/favicon.ico
      create  public/robots.txt
      create  tmp
      create  tmp/.keep
      create  tmp/cache
      create  tmp/cache/assets
      create  vendor
      create  vendor/.keep
      create  test/fixtures
      create  test/fixtures/.keep
      create  test/fixtures/files
      create  test/fixtures/files/.keep
      create  test/controllers
      create  test/controllers/.keep
      create  test/mailers
      create  test/mailers/.keep
      create  test/models
      create  test/models/.keep
      create  test/helpers
      create  test/helpers/.keep
      create  test/integration
      create  test/integration/.keep
      create  test/channels/application_cable/connection_test.rb
      create  test/test_helper.rb
      create  test/system
      create  test/system/.keep
      create  test/application_system_test_case.rb
      create  storage
      create  storage/.keep
      create  tmp/storage
      create  tmp/storage/.keep
      remove  config/initializers/cors.rb
      remove  config/initializers/new_framework_defaults_6_0.rb
         run  bundle install
The dependency tzinfo-data (>= 0) will be unused by any of the platforms Bundler is installing for. Bundler is installing for ruby but the dependency is only for x86-mingw32, x86-mswin32, x64-mingw32, java. To add those platforms to the bundle, run `bundle lock --add-platform x86-mingw32 x86-mswin32 x64-mingw32 java`.
Fetching gem metadata from https://rubygems.org/............
Fetching gem metadata from https://rubygems.org/.
Resolving dependencies....
Using rake 12.3.2
Using concurrent-ruby 1.1.5
Using i18n 1.6.0
Using minitest 5.11.3
Using thread_safe 0.3.6
Using tzinfo 1.2.5
Using zeitwerk 2.1.6
Using activesupport 6.0.0.rc1
Using builder 3.2.3
Using erubi 1.8.0
Using mini_portile2 2.4.0
Using nokogiri 1.10.3
Using rails-dom-testing 2.0.3
Using crass 1.0.4
Using loofah 2.2.3
Using rails-html-sanitizer 1.0.4
Using actionview 6.0.0.rc1
Using rack 2.0.7
Using rack-test 1.1.0
Using actionpack 6.0.0.rc1
Using nio4r 2.3.1
Using websocket-extensions 0.1.3
Using websocket-driver 0.7.0
Using actioncable 6.0.0.rc1
Using globalid 0.4.2
Using activejob 6.0.0.rc1
Using activemodel 6.0.0.rc1
Using activerecord 6.0.0.rc1
Using mimemagic 0.3.3
Using marcel 0.3.3
Using activestorage 6.0.0.rc1
Using mini_mime 1.0.1
Using mail 2.7.1
Using actionmailbox 6.0.0.rc1
Using actionmailer 6.0.0.rc1
Using actiontext 6.0.0.rc1
Using public_suffix 3.1.0
Using addressable 2.6.0
Using bindex 0.7.0
Using msgpack 1.2.10
Using bootsnap 1.4.4
Using bundler 2.0.1
Using byebug 11.0.1
Using regexp_parser 1.5.1
Using xpath 3.2.0
Using capybara 3.22.0
Using childprocess 1.0.1
Using ffi 1.11.1
Using jbuilder 2.9.1
Using rb-fsevent 0.10.3
Using rb-inotify 0.10.0
Using ruby_dep 1.5.0
Using listen 3.1.5
Using method_source 0.9.2
Using puma 3.12.1
Using rack-proxy 0.6.5
Using thor 0.20.3
Using railties 6.0.0.rc1
Using sprockets 3.7.2
Using sprockets-rails 3.2.1
Using rails 6.0.0.rc1
Using rubyzip 1.2.3
Using sass-listen 4.0.0
Using sass 3.7.4
Using tilt 2.0.9
Using sass-rails 5.0.7
Using selenium-webdriver 3.142.3
Using spring 2.0.2
Using spring-watcher-listen 2.0.1
Using sqlite3 1.4.1
Using turbolinks-source 5.2.0
Using turbolinks 5.2.0
Using web-console 4.0.0
Using webdrivers 4.0.0
Using webpacker 4.0.4
Bundle complete! 17 Gemfile dependencies, 75 gems now installed.
Use `bundle info [gemname]` to see where a bundled gem is installed.
         run  bundle binstubs bundler
The dependency tzinfo-data (>= 0) will be unused by any of the platforms Bundler is installing for. Bundler is installing for ruby but the dependency is only for x86-mingw32, x86-mswin32, x64-mingw32, java. To add those platforms to the bundle, run `bundle lock --add-platform x86-mingw32 x86-mswin32 x64-mingw32 java`.
         run  bundle exec spring binstub --all
* bin/rake: spring inserted
* bin/rails: spring inserted
       rails  webpacker:install
RAILS_ENV=development environment is not defined in config/webpacker.yml, falling back to production environment
      create  config/webpacker.yml
Copying webpack core config
      create  config/webpack
      create  config/webpack/development.js
      create  config/webpack/environment.js
      create  config/webpack/production.js
      create  config/webpack/test.js
Copying postcss.config.js to app root directory
      create  postcss.config.js
Copying babel.config.js to app root directory
      create  babel.config.js
Copying .browserslistrc to app root directory
      create  .browserslistrc
The JavaScript app source directory already exists
       apply  /Users/jordan/.asdf/installs/ruby/2.6.3/lib/ruby/gems/2.6.0/gems/webpacker-4.0.4/lib/install/binstubs.rb
  Copying binstubs
       exist    bin
      create    bin/webpack
      create    bin/webpack-dev-server
      append  .gitignore
Installing all JavaScript dependencies [4.0.4]
         run  yarn add @rails/webpacker from "."
yarn add v1.6.0
info No lockfile found.
[1/4] 🔍  Resolving packages...
warning @rails/webpacker > postcss-preset-env > postcss-color-functional-notation > postcss-values-parser > flatten@1.0.2: I wrote this module a very long time ago; you should use something else.
[2/4] 🚚  Fetching packages...
[3/4] 🔗  Linking dependencies...
warning "@rails/webpacker > pnp-webpack-plugin > ts-pnp@1.1.2" has unmet peer dependency "typescript@*".
[4/4] 📃  Building fresh packages...
success Saved lockfile.
success Saved 601 new dependencies.
info Direct dependencies
├─ @rails/actioncable@6.0.0-alpha
├─ @rails/activestorage@6.0.0-alpha
├─ @rails/ujs@6.0.0-alpha
├─ @rails/webpacker@4.0.4
└─ turbolinks@5.2.0
info All dependencies
├─ @babel/core@7.4.5
├─ @babel/helper-builder-binary-assignment-operator-visitor@7.1.0
├─ @babel/helper-call-delegate@7.4.4
├─ @babel/helper-create-class-features-plugin@7.4.4
├─ @babel/helper-define-map@7.4.4
├─ @babel/helper-explode-assignable-expression@7.1.0
├─ @babel/helper-replace-supers@7.4.4
├─ @babel/helper-wrap-function@7.2.0
├─ @babel/helpers@7.4.4
├─ @babel/highlight@7.0.0
├─ @babel/parser@7.4.5
├─ @babel/plugin-proposal-async-generator-functions@7.2.0
├─ @babel/plugin-proposal-class-properties@7.4.4
├─ @babel/plugin-proposal-json-strings@7.2.0
├─ @babel/plugin-proposal-optional-catch-binding@7.2.0
├─ @babel/plugin-proposal-unicode-property-regex@7.4.4
├─ @babel/plugin-syntax-dynamic-import@7.2.0
├─ @babel/plugin-transform-arrow-functions@7.2.0
├─ @babel/plugin-transform-async-to-generator@7.4.4
├─ @babel/plugin-transform-block-scoped-functions@7.2.0
├─ @babel/plugin-transform-block-scoping@7.4.4
├─ @babel/plugin-transform-classes@7.4.4
├─ @babel/plugin-transform-computed-properties@7.2.0
├─ @babel/plugin-transform-dotall-regex@7.4.4
├─ @babel/plugin-transform-duplicate-keys@7.2.0
├─ @babel/plugin-transform-exponentiation-operator@7.2.0
├─ @babel/plugin-transform-for-of@7.4.4
├─ @babel/plugin-transform-function-name@7.4.4
├─ @babel/plugin-transform-literals@7.2.0
├─ @babel/plugin-transform-member-expression-literals@7.2.0
├─ @babel/plugin-transform-modules-amd@7.2.0
├─ @babel/plugin-transform-modules-commonjs@7.4.4
├─ @babel/plugin-transform-modules-systemjs@7.4.4
├─ @babel/plugin-transform-modules-umd@7.2.0
├─ @babel/plugin-transform-named-capturing-groups-regex@7.4.5
├─ @babel/plugin-transform-new-target@7.4.4
├─ @babel/plugin-transform-object-super@7.2.0
├─ @babel/plugin-transform-parameters@7.4.4
├─ @babel/plugin-transform-property-literals@7.2.0
├─ @babel/plugin-transform-reserved-words@7.2.0
├─ @babel/plugin-transform-runtime@7.4.4
├─ @babel/plugin-transform-shorthand-properties@7.2.0
├─ @babel/plugin-transform-spread@7.2.2
├─ @babel/plugin-transform-sticky-regex@7.2.0
├─ @babel/plugin-transform-template-literals@7.4.4
├─ @babel/plugin-transform-typeof-symbol@7.2.0
├─ @babel/plugin-transform-unicode-regex@7.4.4
├─ @babel/preset-env@7.4.5
├─ @babel/runtime-corejs3@7.4.5
├─ @babel/runtime@7.4.5
├─ @rails/actioncable@6.0.0-alpha
├─ @rails/activestorage@6.0.0-alpha
├─ @rails/ujs@6.0.0-alpha
├─ @rails/webpacker@4.0.4
├─ @types/q@1.5.2
├─ @webassemblyjs/floating-point-hex-parser@1.8.5
├─ @webassemblyjs/helper-code-frame@1.8.5
├─ @webassemblyjs/helper-fsm@1.8.5
├─ @webassemblyjs/helper-wasm-section@1.8.5
├─ @webassemblyjs/wasm-edit@1.8.5
├─ @webassemblyjs/wasm-opt@1.8.5
├─ @xtuc/ieee754@1.2.0
├─ abbrev@1.1.1
├─ acorn-dynamic-import@4.0.0
├─ acorn@6.1.1
├─ ajv-errors@1.0.1
├─ ajv@6.10.0
├─ amdefine@1.0.1
├─ ansi-styles@3.2.1
├─ anymatch@2.0.0
├─ are-we-there-yet@1.1.5
├─ argparse@1.0.10
├─ arr-flatten@1.1.0
├─ array-find-index@1.0.2
├─ asn1.js@4.10.1
├─ asn1@0.2.4
├─ assert@1.5.0
├─ assign-symbols@1.0.0
├─ async-each@1.0.3
├─ async-foreach@0.1.3
├─ asynckit@0.4.0
├─ atob@2.1.2
├─ autoprefixer@9.5.1
├─ aws-sign2@0.7.0
├─ aws4@1.8.0
├─ babel-loader@8.0.6
├─ babel-plugin-dynamic-import-node@2.2.0
├─ babel-plugin-macros@2.5.1
├─ base@0.11.2
├─ base64-js@1.3.0
├─ bcrypt-pbkdf@1.0.2
├─ big.js@5.2.2
├─ binary-extensions@1.13.1
├─ block-stream@0.0.9
├─ bluebird@3.5.5
├─ boolbase@1.0.0
├─ brace-expansion@1.1.11
├─ braces@2.3.2
├─ browserify-aes@1.2.0
├─ browserify-cipher@1.0.1
├─ browserify-des@1.0.2
├─ browserify-sign@4.0.4
├─ browserify-zlib@0.2.0
├─ buffer-xor@1.0.3
├─ buffer@4.9.1
├─ builtin-status-codes@3.0.0
├─ cacache@11.3.2
├─ cache-base@1.0.1
├─ caller-callsite@2.0.0
├─ caller-path@2.0.0
├─ callsites@2.0.0
├─ camelcase-keys@2.1.0
├─ caniuse-lite@1.0.30000971
├─ case-sensitive-paths-webpack-plugin@2.2.0
├─ caseless@0.12.0
├─ chokidar@2.1.6
├─ chownr@1.1.1
├─ chrome-trace-event@1.0.2
├─ class-utils@0.3.6
├─ cliui@4.1.0
├─ clone-deep@2.0.2
├─ coa@2.0.2
├─ code-point-at@1.1.0
├─ collection-visit@1.0.0
├─ color-convert@1.9.3
├─ color-name@1.1.3
├─ color-string@1.5.3
├─ color@3.1.1
├─ combined-stream@1.0.8
├─ commander@2.20.0
├─ commondir@1.0.1
├─ compression-webpack-plugin@2.0.0
├─ concat-map@0.0.1
├─ concat-stream@1.6.2
├─ console-browserify@1.1.0
├─ console-control-strings@1.1.0
├─ constants-browserify@1.0.0
├─ convert-source-map@1.6.0
├─ copy-concurrently@1.0.5
├─ copy-descriptor@0.1.1
├─ core-js-compat@3.1.3
├─ core-js-pure@3.1.3
├─ core-js@3.1.3
├─ core-util-is@1.0.2
├─ cosmiconfig@5.2.1
├─ create-ecdh@4.0.3
├─ create-hmac@1.1.7
├─ cross-spawn@6.0.5
├─ crypto-browserify@3.12.0
├─ css-blank-pseudo@0.1.4
├─ css-color-names@0.0.4
├─ css-declaration-sorter@4.0.1
├─ css-has-pseudo@0.10.0
├─ css-loader@2.1.1
├─ css-prefers-color-scheme@3.1.1
├─ css-select-base-adapter@0.1.1
├─ css-select@2.0.2
├─ css-tree@1.0.0-alpha.28
├─ css-unit-converter@1.1.1
├─ css-url-regex@1.1.0
├─ css-what@2.1.3
├─ cssdb@4.4.0
├─ cssesc@2.0.0
├─ cssnano-preset-default@4.0.7
├─ cssnano-util-raw-cache@4.0.1
├─ cssnano-util-same-parent@4.0.1
├─ cssnano@4.1.10
├─ csso@3.5.1
├─ currently-unhandled@0.4.1
├─ cyclist@0.2.2
├─ dashdash@1.14.1
├─ date-now@0.1.4
├─ debug@2.6.9
├─ decode-uri-component@0.2.0
├─ deep-extend@0.6.0
├─ delayed-stream@1.0.0
├─ delegates@1.0.0
├─ des.js@1.0.0
├─ detect-file@1.0.0
├─ detect-libc@1.0.3
├─ diffie-hellman@5.0.3
├─ dom-serializer@0.1.1
├─ domain-browser@1.2.0
├─ domelementtype@1.3.1
├─ domutils@1.7.0
├─ dot-prop@4.2.0
├─ duplexify@3.7.1
├─ ecc-jsbn@0.1.2
├─ electron-to-chromium@1.3.139
├─ emojis-list@2.1.0
├─ entities@1.1.2
├─ errno@0.1.7
├─ error-ex@1.3.2
├─ es-abstract@1.13.0
├─ es-to-primitive@1.2.0
├─ escape-string-regexp@1.0.5
├─ eslint-scope@4.0.3
├─ esprima@4.0.1
├─ esrecurse@4.2.1
├─ estraverse@4.2.0
├─ events@3.0.0
├─ execa@1.0.0
├─ expand-brackets@2.1.4
├─ expand-tilde@2.0.2
├─ extend@3.0.2
├─ extglob@2.0.4
├─ extsprintf@1.3.0
├─ fast-deep-equal@2.0.1
├─ fast-json-stable-stringify@2.0.0
├─ file-loader@3.0.1
├─ fill-range@4.0.0
├─ findup-sync@2.0.0
├─ flatted@2.0.0
├─ flatten@1.0.2
├─ flush-write-stream@1.1.1
├─ for-in@1.0.2
├─ for-own@1.0.0
├─ forever-agent@0.6.1
├─ form-data@2.3.3
├─ from2@2.3.0
├─ fs-minipass@1.2.6
├─ fs.realpath@1.0.0
├─ fsevents@1.2.9
├─ fstream@1.0.12
├─ gauge@2.7.4
├─ gaze@1.1.3
├─ get-stream@4.1.0
├─ get-value@2.0.6
├─ getpass@0.1.7
├─ glob-parent@3.1.0
├─ glob@7.1.4
├─ global-prefix@1.0.2
├─ globule@1.2.1
├─ har-schema@2.0.0
├─ har-validator@5.1.3
├─ has-ansi@2.0.0
├─ has-unicode@2.0.1
├─ has-value@1.0.0
├─ has-values@1.0.0
├─ has@1.0.3
├─ hash.js@1.1.7
├─ hex-color-regex@1.1.0
├─ hmac-drbg@1.0.1
├─ hosted-git-info@2.7.1
├─ hsl-regex@1.0.0
├─ hsla-regex@1.0.0
├─ html-comment-regex@1.1.2
├─ http-signature@1.2.0
├─ https-browserify@1.0.0
├─ iconv-lite@0.4.24
├─ icss-replace-symbols@1.1.0
├─ icss-utils@4.1.1
├─ ieee754@1.1.13
├─ ignore-walk@3.0.1
├─ import-cwd@2.1.0
├─ import-fresh@2.0.0
├─ import-from@2.1.0
├─ import-local@2.0.0
├─ in-publish@2.0.0
├─ indent-string@2.1.0
├─ indexof@0.0.1
├─ inflight@1.0.6
├─ ini@1.3.5
├─ interpret@1.2.0
├─ invariant@2.2.4
├─ invert-kv@2.0.0
├─ is-absolute-url@2.1.0
├─ is-accessor-descriptor@1.0.0
├─ is-arrayish@0.2.1
├─ is-binary-path@1.0.1
├─ is-color-stop@1.1.0
├─ is-data-descriptor@1.0.0
├─ is-date-object@1.0.1
├─ is-descriptor@1.0.2
├─ is-extglob@2.1.1
├─ is-finite@1.0.2
├─ is-fullwidth-code-point@1.0.0
├─ is-obj@1.0.1
├─ is-plain-obj@1.1.0
├─ is-plain-object@2.0.4
├─ is-regex@1.0.4
├─ is-resolvable@1.1.0
├─ is-stream@1.1.0
├─ is-svg@3.0.0
├─ is-symbol@1.0.2
├─ is-typedarray@1.0.0
├─ is-utf8@0.2.1
├─ is-windows@1.0.2
├─ is-wsl@1.1.0
├─ isarray@1.0.0
├─ isexe@2.0.0
├─ isstream@0.1.2
├─ js-base64@2.5.1
├─ js-levenshtein@1.1.6
├─ js-tokens@4.0.0
├─ jsesc@2.5.2
├─ json-parse-better-errors@1.0.2
├─ json-schema-traverse@0.4.1
├─ json-schema@0.2.3
├─ json-stringify-safe@5.0.1
├─ json5@2.1.0
├─ jsprim@1.4.1
├─ kind-of@3.2.2
├─ last-call-webpack-plugin@3.0.0
├─ lcid@2.0.0
├─ load-json-file@1.1.0
├─ loader-runner@2.4.0
├─ locate-path@3.0.0
├─ lodash.get@4.4.2
├─ lodash.has@4.5.2
├─ lodash.memoize@4.1.2
├─ lodash.tail@4.1.1
├─ lodash.template@4.4.0
├─ lodash.templatesettings@4.1.0
├─ lodash.uniq@4.5.0
├─ lodash@4.17.11
├─ loose-envify@1.4.0
├─ loud-rejection@1.6.0
├─ lru-cache@4.1.5
├─ make-dir@2.1.0
├─ mamacro@0.0.3
├─ map-age-cleaner@0.1.3
├─ map-obj@1.0.1
├─ map-visit@1.0.0
├─ mem@4.3.0
├─ memory-fs@0.4.1
├─ meow@3.7.0
├─ micromatch@3.1.10
├─ miller-rabin@4.0.1
├─ mime-db@1.40.0
├─ mime-types@2.1.24
├─ mimic-fn@2.1.0
├─ mini-css-extract-plugin@0.7.0
├─ minimalistic-crypto-utils@1.0.1
├─ minimatch@3.0.4
├─ minimist@1.2.0
├─ minizlib@1.2.1
├─ mississippi@3.0.0
├─ mixin-deep@1.3.1
├─ mixin-object@2.0.1
├─ mkdirp@0.5.1
├─ move-concurrently@1.0.1
├─ ms@2.1.1
├─ nan@2.14.0
├─ nanomatch@1.2.13
├─ needle@2.4.0
├─ nice-try@1.0.5
├─ node-gyp@3.8.0
├─ node-libs-browser@2.2.0
├─ node-pre-gyp@0.12.0
├─ node-releases@1.1.22
├─ node-sass@4.12.0
├─ nopt@3.0.6
├─ normalize-package-data@2.5.0
├─ normalize-range@0.1.2
├─ normalize-url@1.9.1
├─ npm-bundled@1.0.6
├─ npm-packlist@1.4.1
├─ npm-run-path@2.0.2
├─ npmlog@4.1.2
├─ nth-check@1.0.2
├─ num2fraction@1.2.2
├─ oauth-sign@0.9.0
├─ object-assign@4.1.1
├─ object-copy@0.1.0
├─ object.assign@4.1.0
├─ object.getownpropertydescriptors@2.0.3
├─ object.values@1.1.0
├─ once@1.4.0
├─ optimize-css-assets-webpack-plugin@5.0.1
├─ os-browserify@0.3.0
├─ os-homedir@1.0.2
├─ os-locale@3.1.0
├─ os-tmpdir@1.0.2
├─ osenv@0.1.5
├─ p-defer@1.0.0
├─ p-finally@1.0.0
├─ p-is-promise@2.1.0
├─ p-limit@2.2.0
├─ p-locate@3.0.0
├─ p-try@2.2.0
├─ pako@1.0.10
├─ parallel-transform@1.1.0
├─ parse-passwd@1.0.0
├─ pascalcase@0.1.1
├─ path-browserify@0.0.0
├─ path-complete-extname@1.0.0
├─ path-dirname@1.0.2
├─ path-exists@3.0.0
├─ path-key@2.0.1
├─ path-parse@1.0.6
├─ path-type@1.1.0
├─ performance-now@2.1.0
├─ pinkie@2.0.4
├─ pnp-webpack-plugin@1.4.3
├─ posix-character-classes@0.1.1
├─ postcss-attribute-case-insensitive@4.0.1
├─ postcss-calc@7.0.1
├─ postcss-color-functional-notation@2.0.1
├─ postcss-color-gray@5.0.0
├─ postcss-color-hex-alpha@5.0.3
├─ postcss-color-mod-function@3.0.3
├─ postcss-color-rebeccapurple@4.0.1
├─ postcss-colormin@4.0.3
├─ postcss-convert-values@4.0.1
├─ postcss-custom-media@7.0.8
├─ postcss-custom-properties@8.0.10
├─ postcss-custom-selectors@5.1.2
├─ postcss-dir-pseudo-class@5.0.0
├─ postcss-discard-comments@4.0.2
├─ postcss-discard-duplicates@4.0.2
├─ postcss-discard-empty@4.0.1
├─ postcss-discard-overridden@4.0.1
├─ postcss-double-position-gradients@1.0.0
├─ postcss-env-function@2.0.2
├─ postcss-flexbugs-fixes@4.1.0
├─ postcss-focus-visible@4.0.0
├─ postcss-focus-within@3.0.0
├─ postcss-font-variant@4.0.0
├─ postcss-gap-properties@2.0.0
├─ postcss-image-set-function@3.0.1
├─ postcss-import@12.0.1
├─ postcss-initial@3.0.0
├─ postcss-lab-function@2.0.1
├─ postcss-load-config@2.0.0
├─ postcss-loader@3.0.0
├─ postcss-logical@3.0.0
├─ postcss-media-minmax@4.0.0
├─ postcss-merge-longhand@4.0.11
├─ postcss-merge-rules@4.0.3
├─ postcss-minify-font-values@4.0.2
├─ postcss-minify-gradients@4.0.2
├─ postcss-minify-params@4.0.2
├─ postcss-minify-selectors@4.0.2
├─ postcss-modules-extract-imports@2.0.0
├─ postcss-modules-local-by-default@2.0.6
├─ postcss-modules-scope@2.1.0
├─ postcss-modules-values@2.0.0
├─ postcss-nesting@7.0.0
├─ postcss-normalize-charset@4.0.1
├─ postcss-normalize-display-values@4.0.2
├─ postcss-normalize-positions@4.0.2
├─ postcss-normalize-repeat-style@4.0.2
├─ postcss-normalize-string@4.0.2
├─ postcss-normalize-timing-functions@4.0.2
├─ postcss-normalize-unicode@4.0.1
├─ postcss-normalize-url@4.0.1
├─ postcss-normalize-whitespace@4.0.2
├─ postcss-ordered-values@4.1.2
├─ postcss-overflow-shorthand@2.0.0
├─ postcss-page-break@2.0.0
├─ postcss-place@4.0.1
├─ postcss-preset-env@6.6.0
├─ postcss-pseudo-class-any-link@6.0.0
├─ postcss-reduce-initial@4.0.3
├─ postcss-reduce-transforms@4.0.2
├─ postcss-replace-overflow-wrap@3.0.0
├─ postcss-safe-parser@4.0.1
├─ postcss-selector-matches@4.0.0
├─ postcss-selector-not@4.0.0
├─ postcss-svgo@4.0.2
├─ postcss-unique-selectors@4.0.1
├─ prepend-http@1.0.4
├─ private@0.1.8
├─ process-nextick-args@2.0.0
├─ process@0.11.10
├─ promise-inflight@1.0.1
├─ prr@1.0.1
├─ pseudomap@1.0.2
├─ psl@1.1.32
├─ public-encrypt@4.0.3
├─ pumpify@1.5.1
├─ punycode@1.4.1
├─ q@1.5.1
├─ qs@6.5.2
├─ query-string@4.3.4
├─ querystring-es3@0.2.1
├─ querystring@0.2.0
├─ randomfill@1.0.4
├─ rc@1.2.8
├─ read-cache@1.0.0
├─ read-pkg@1.1.0
├─ readdirp@2.2.1
├─ redent@1.0.0
├─ regenerate-unicode-properties@8.1.0
├─ regenerator-transform@0.14.0
├─ regexp-tree@0.1.10
├─ regjsgen@0.5.0
├─ regjsparser@0.6.0
├─ remove-trailing-separator@1.1.0
├─ repeat-element@1.1.3
├─ repeating@2.0.1
├─ request@2.88.0
├─ require-from-string@2.0.2
├─ resolve-cwd@2.0.0
├─ resolve-dir@1.0.1
├─ resolve-url@0.2.1
├─ ret@0.1.15
├─ rgb-regex@1.0.1
├─ rgba-regex@1.0.0
├─ rimraf@2.6.3
├─ run-queue@1.0.3
├─ safer-buffer@2.1.2
├─ sass-graph@2.2.4
├─ sass-loader@7.1.0
├─ sax@1.2.4
├─ scss-tokenizer@0.2.3
├─ semver@5.7.0
├─ serialize-javascript@1.7.0
├─ set-value@2.0.0
├─ setimmediate@1.0.5
├─ shallow-clone@1.0.0
├─ shebang-command@1.2.0
├─ shebang-regex@1.0.0
├─ simple-swizzle@0.2.2
├─ snapdragon-node@2.1.1
├─ snapdragon-util@3.0.1
├─ sort-keys@1.1.2
├─ source-list-map@2.0.1
├─ source-map-resolve@0.5.2
├─ source-map-support@0.5.12
├─ source-map-url@0.4.0
├─ spark-md5@3.0.0
├─ spdx-correct@3.1.0
├─ spdx-exceptions@2.2.0
├─ split-string@3.1.0
├─ sprintf-js@1.0.3
├─ sshpk@1.16.1
├─ ssri@6.0.1
├─ stable@0.1.8
├─ static-extend@0.1.2
├─ stdout-stream@1.4.1
├─ stream-browserify@2.0.2
├─ stream-each@1.2.3
├─ stream-http@2.8.3
├─ strict-uri-encode@1.1.0
├─ string_decoder@1.2.0
├─ strip-bom@2.0.0
├─ strip-eof@1.0.0
├─ strip-indent@1.0.1
├─ strip-json-comments@2.0.1
├─ style-loader@0.23.1
├─ stylehacks@4.0.3
├─ supports-color@5.5.0
├─ svgo@1.2.2
├─ tar@2.2.2
├─ terser-webpack-plugin@1.3.0
├─ terser@4.0.0
├─ through2@2.0.5
├─ timers-browserify@2.0.10
├─ timsort@0.3.0
├─ to-arraybuffer@1.0.1
├─ to-fast-properties@2.0.0
├─ to-regex-range@2.1.1
├─ tough-cookie@2.4.3
├─ trim-newlines@1.0.0
├─ trim-right@1.0.1
├─ true-case-path@1.0.3
├─ ts-pnp@1.1.2
├─ tslib@1.9.3
├─ tty-browserify@0.0.0
├─ tunnel-agent@0.6.0
├─ turbolinks@5.2.0
├─ tweetnacl@0.14.5
├─ typedarray@0.0.6
├─ unicode-canonical-property-names-ecmascript@1.0.4
├─ unicode-match-property-ecmascript@1.0.4
├─ unicode-match-property-value-ecmascript@1.1.0
├─ unicode-property-aliases-ecmascript@1.0.5
├─ union-value@1.0.0
├─ unique-filename@1.1.1
├─ unique-slug@2.0.1
├─ unquote@1.1.1
├─ unset-value@1.0.0
├─ upath@1.1.2
├─ uri-js@4.2.2
├─ urix@0.1.0
├─ url@0.11.0
├─ use@3.1.1
├─ util-deprecate@1.0.2
├─ util.promisify@1.0.0
├─ util@0.11.1
├─ uuid@3.3.2
├─ v8-compile-cache@2.0.3
├─ validate-npm-package-license@3.0.4
├─ vendors@1.0.3
├─ verror@1.10.0
├─ vm-browserify@0.0.4
├─ watchpack@1.6.0
├─ webpack-assets-manifest@3.1.1
├─ webpack-cli@3.3.2
├─ webpack@4.32.2
├─ which-module@2.0.0
├─ which@1.3.1
├─ wide-align@1.1.3
├─ worker-farm@1.7.0
├─ xtend@4.0.1
├─ y18n@4.0.0
├─ yallist@3.0.3
├─ yargs-parser@11.1.1
└─ yargs@12.0.5
✨  Done in 17.51s.
Installing dev server for live reloading
         run  yarn add --dev webpack-dev-server from "."
yarn add v1.6.0
[1/4] 🔍  Resolving packages...
[2/4] 🚚  Fetching packages...
[3/4] 🔗  Linking dependencies...
warning "@rails/webpacker > pnp-webpack-plugin > ts-pnp@1.1.2" has unmet peer dependency "typescript@*".
warning "webpack-dev-server > webpack-dev-middleware@3.7.0" has unmet peer dependency "webpack@^4.0.0".
warning " > webpack-dev-server@3.4.1" has unmet peer dependency "webpack@^4.0.0".
[4/4] 📃  Building fresh packages...
success Saved lockfile.
success Saved 92 new dependencies.
info Direct dependencies
└─ webpack-dev-server@3.4.1
info All dependencies
├─ @types/events@3.0.0
├─ @types/glob@7.1.1
├─ @types/minimatch@3.0.3
├─ @types/node@12.0.3
├─ accepts@1.3.7
├─ ansi-colors@3.2.4
├─ ansi-html@0.0.7
├─ array-flatten@1.1.1
├─ array-union@1.0.2
├─ array-uniq@1.0.3
├─ async@1.5.2
├─ batch@0.6.1
├─ body-parser@1.19.0
├─ bonjour@3.5.0
├─ buffer-indexof@1.1.1
├─ compressible@2.0.17
├─ compression@1.7.4
├─ connect-history-api-fallback@1.6.0
├─ content-disposition@0.5.3
├─ cookie-signature@1.0.6
├─ cookie@0.4.0
├─ deep-equal@1.0.1
├─ default-gateway@4.2.0
├─ del@4.1.1
├─ destroy@1.0.4
├─ detect-node@2.0.4
├─ dns-equal@1.0.0
├─ dns-packet@1.3.1
├─ dns-txt@2.0.2
├─ ee-first@1.1.1
├─ eventemitter3@3.1.2
├─ eventsource@1.0.7
├─ express@4.17.1
├─ faye-websocket@0.10.0
├─ finalhandler@1.1.2
├─ follow-redirects@1.7.0
├─ forwarded@0.1.2
├─ globby@6.1.0
├─ handle-thing@2.0.0
├─ hpack.js@2.1.6
├─ html-entities@1.2.1
├─ http-deceiver@1.2.7
├─ http-parser-js@0.5.0
├─ http-proxy-middleware@0.19.1
├─ http-proxy@1.17.0
├─ internal-ip@4.3.0
├─ ip-regex@2.1.0
├─ ip@1.1.5
├─ ipaddr.js@1.9.0
├─ is-path-cwd@2.1.0
├─ is-path-in-cwd@2.1.0
├─ is-path-inside@2.1.0
├─ json3@3.3.3
├─ killable@1.0.1
├─ loglevel@1.6.2
├─ media-typer@0.3.0
├─ merge-descriptors@1.0.1
├─ methods@1.1.2
├─ mime@2.4.3
├─ multicast-dns-service-types@1.1.0
├─ multicast-dns@6.2.3
├─ negotiator@0.6.2
├─ node-forge@0.7.5
├─ obuf@1.1.2
├─ on-headers@1.0.2
├─ opn@5.5.0
├─ original@1.0.2
├─ p-map@2.1.0
├─ path-is-inside@1.0.2
├─ path-to-regexp@0.1.7
├─ portfinder@1.0.20
├─ proxy-addr@2.0.5
├─ querystringify@2.1.1
├─ raw-body@2.4.0
├─ select-hose@2.0.0
├─ selfsigned@1.10.4
├─ serve-index@1.9.1
├─ serve-static@1.14.1
├─ sockjs-client@1.3.0
├─ sockjs@0.3.19
├─ spdy-transport@3.0.0
├─ spdy@4.0.0
├─ statuses@1.5.0
├─ thunky@1.0.3
├─ toidentifier@1.0.0
├─ type-is@1.6.18
├─ unpipe@1.0.0
├─ utils-merge@1.0.1
├─ wbuf@1.7.3
├─ webpack-dev-middleware@3.7.0
├─ webpack-dev-server@3.4.1
└─ websocket-extensions@0.1.3
✨  Done in 4.41s.
Webpacker successfully installed 🎉 🍰



$ cd example-already-watched



$ git add -A



$ git commit -m 'Blank app'
[master (root-commit) aacc737] Blank app
 91 files changed, 7765 insertions(+)
 create mode 100644 .browserslistrc
 create mode 100644 .gitignore
 create mode 100644 .ruby-version
 create mode 100644 Gemfile
 create mode 100644 Gemfile.lock
 create mode 100644 README.md
 create mode 100644 Rakefile
 create mode 100644 app/assets/config/manifest.js
 create mode 100644 app/assets/images/.keep
 create mode 100644 app/assets/stylesheets/application.css
 create mode 100644 app/channels/application_cable/channel.rb
 create mode 100644 app/channels/application_cable/connection.rb
 create mode 100644 app/controllers/application_controller.rb
 create mode 100644 app/controllers/concerns/.keep
 create mode 100644 app/helpers/application_helper.rb
 create mode 100644 app/javascript/channels/consumer.js
 create mode 100644 app/javascript/channels/index.js
 create mode 100644 app/javascript/packs/application.js
 create mode 100644 app/jobs/application_job.rb
 create mode 100644 app/mailers/application_mailer.rb
 create mode 100644 app/models/application_record.rb
 create mode 100644 app/models/concerns/.keep
 create mode 100644 app/views/layouts/application.html.erb
 create mode 100644 app/views/layouts/mailer.html.erb
 create mode 100644 app/views/layouts/mailer.text.erb
 create mode 100644 babel.config.js
 create mode 100755 bin/bundle
 create mode 100755 bin/rails
 create mode 100755 bin/rake
 create mode 100755 bin/setup
 create mode 100755 bin/spring
 create mode 100755 bin/webpack
 create mode 100755 bin/webpack-dev-server
 create mode 100755 bin/yarn
 create mode 100644 config.ru
 create mode 100644 config/application.rb
 create mode 100644 config/boot.rb
 create mode 100644 config/cable.yml
 create mode 100644 config/credentials.yml.enc
 create mode 100644 config/database.yml
 create mode 100644 config/environment.rb
 create mode 100644 config/environments/development.rb
 create mode 100644 config/environments/production.rb
 create mode 100644 config/environments/test.rb
 create mode 100644 config/initializers/application_controller_renderer.rb
 create mode 100644 config/initializers/assets.rb
 create mode 100644 config/initializers/backtrace_silencers.rb
 create mode 100644 config/initializers/content_security_policy.rb
 create mode 100644 config/initializers/cookies_serializer.rb
 create mode 100644 config/initializers/filter_parameter_logging.rb
 create mode 100644 config/initializers/inflections.rb
 create mode 100644 config/initializers/mime_types.rb
 create mode 100644 config/initializers/wrap_parameters.rb
 create mode 100644 config/locales/en.yml
 create mode 100644 config/puma.rb
 create mode 100644 config/routes.rb
 create mode 100644 config/spring.rb
 create mode 100644 config/storage.yml
 create mode 100644 config/webpack/development.js
 create mode 100644 config/webpack/environment.js
 create mode 100644 config/webpack/production.js
 create mode 100644 config/webpack/test.js
 create mode 100644 config/webpacker.yml
 create mode 100644 db/seeds.rb
 create mode 100644 lib/assets/.keep
 create mode 100644 lib/tasks/.keep
 create mode 100644 log/.keep
 create mode 100644 package.json
 create mode 100644 postcss.config.js
 create mode 100644 public/404.html
 create mode 100644 public/422.html
 create mode 100644 public/500.html
 create mode 100644 public/apple-touch-icon-precomposed.png
 create mode 100644 public/apple-touch-icon.png
 create mode 100644 public/favicon.ico
 create mode 100644 public/robots.txt
 create mode 100644 storage/.keep
 create mode 100644 test/application_system_test_case.rb
 create mode 100644 test/channels/application_cable/connection_test.rb
 create mode 100644 test/controllers/.keep
 create mode 100644 test/fixtures/.keep
 create mode 100644 test/fixtures/files/.keep
 create mode 100644 test/helpers/.keep
 create mode 100644 test/integration/.keep
 create mode 100644 test/mailers/.keep
 create mode 100644 test/models/.keep
 create mode 100644 test/system/.keep
 create mode 100644 test/test_helper.rb
 create mode 100644 tmp/.keep
 create mode 100644 vendor/.keep
 create mode 100644 yarn.lock



$ spring stop && rails console
        ** ERROR: directory is already being watched! **

        Directory: /private/tmp/example-already-watched/node_modules/.bin/compression-webpack-plugin

        is already being watched through: /private/tmp/example-already-watched/node_modules/compression-webpack-plugin

        MORE INFO: https://github.com/guard/listen/wiki/Duplicate-directory-errors
        ** ERROR: directory is already being watched! **

        Directory: /private/tmp/example-already-watched/node_modules/@rails/webpacker/node_modules/.bin/compression-webpack-plugin

        is already being watched through: /private/tmp/example-already-watched/node_modules/compression-webpack-plugin

        MORE INFO: https://github.com/guard/listen/wiki/Duplicate-directory-errors
Running via Spring preloader in process 36709
Loading development environment (Rails 6.0.0.rc1)
irb(main):001:0> 
```
