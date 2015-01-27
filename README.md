When writing own packages, it is required to pull some of packages from Meteor in order to work.
For example, `templating` for `Template.[templateName].helpers()` to work

```js
Package.onUse(function (api) {
    api.versionsFrom("1.0");
    api.use('templating');
    api.use('session');
    api.use('reactive-var');
});

```

Common pattern `package.js`

```js
Package.describe({
  // Replace `name:package-name` to your own account name and package name
  name: 'name:package-name',
  version: '1.0.0',
  // Brief, one-line summary of the package.
  summary: 'package-summary',
  // URL to the Git repository containing the source code for this package.
  git: '',
  // By default, Meteor will default to using README.md for documentation.
  // To avoid submitting documentation, set this field to null.
  documentation: 'README.md'
});

Package.onUse(function (api) {
  api.versionsFrom('1.0');

  // Include Libraries
  api.use([
    'templating',
    'reactive-var',
    'session',
    'less',
    'iron:router'
  ]);

  // All Environments
  api.addFiles([
    // ...
  ]);

  // Client-only Files
  api.addFiles([
    // ...
  ], 'client');

  // Server-only Files
  api.addFiles([
    // ...
  ], 'server');
});

Package.onTest(function (api) {
  api.use('tinytest');
  api.use('name:package-name');
  api.addFiles('name:package-name-tests.js');
});

```







## List of Packages used in Meteor.js

```
accounts-base
accounts-facebook
accounts-github
accounts-google
accounts-meetup
accounts-meteor-developer
accounts-oauth
accounts-password
accounts-twitter
accounts-ui-unstyled
accounts-ui
accounts-weibo
appcache
application-configuration
audit-argument-checks
autopublish
autoupdate
base64
binary-heap
blaze-tools
blaze
boilerplate-generator
browser-policy-common
browser-policy-content
browser-policy-framing
browser-policy
callback-hook
check
code-prettify
coffeescript-test-helper
coffeescript
constraint-solver
ctl-helper
ctl
ddp
deprecated
deps
dev-bundle-fetcher
disable-oplog
ejson
email
facebook
facts
fastclick
follower-livedata
force-ssl
geojson-utils
github
google
handlebars
html-tools
htmljs
http
id-map
insecure
jquery-waypoints
jquery
js-analyze-tests
js-analyze
json
jsparse
launch-screen
less
livedata
localstorage
logging
markdown
meetup
meteor-developer
meteor-platform
meteor-tool
meteor
meyerweb-reset
minifiers
minimongo
mobile-status-bar
mongo-livedata
mongo
non-core
oauth-encryption
oauth
oauth1
oauth2
observe-sequence
ordered-dict
package-stats-opt-out
package-version-parser
preserve-inputs
random
reactive-dict
reactive-var
reload-safetybelt
reload
retry
routepolicy
service-configuration
session
sha
showdown
spacebars-compiler
spacebars-tests
spacebars
spiderable
srp
standard-app-packages
star-translate
startup
stylus
templating
test-helpers
test-in-browser
test-in-console
test-server-tests-in-console-once
tinytest
tracker
twitter
ui
underscore-tests
underscore
url
webapp-hashing
webapp
weibo
xmlbuilder
```