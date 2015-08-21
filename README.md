## List of Userful Packages
```
telerik:kendo-ui-core-default-theme           - Kendo UI 
mjn:famous                                    - Famo.us framework intergration, UI designs
awsp:validatejs                               - Validate.js
underscore                                    - Underscore Library
iron:layout                                   - Iron Layout, dynamic layout
iron:router                                   - Iron Router, routing
accounts-base, accounts-ui, accounts-password - Authentication
sanjo:jasmine                                 - Jasmine BDD Testing Frameworks
velocity:html-reporter                        - Testing UI, reporter
momentjs:moment                               - MomentJS, date, time calculation, formatter
benmgreene:moment-range                       - MomentJS Range
less                                          - Less support
urigo:angular                                 - AngularJS intergration
kadira:flow-router-ssr                        - Similar to Iron Router, this package of flow router comes with SSR support, bring better SEO to Meteor.js, see example: https://github.com/awsp/hello-react-meteor
kadira:dochead                                - Used to control document head section in Meteor.js, combines with flow-router-ssr will give page source code get its own title and meta tags.
wolves:bourbon                                - Bourbon is a library of pure Sass mixins that are designed to be simple and easy to use. 
wolves:neat                                   - A lightweight, semantic grid framework built on top of Bourbon.
wolves:bitters                                - Scaffold styles, variables and structure for Bourbon projects.
```



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
base64
blaze
code-prettify
coffeescript
ejson
email
facebook
force-ssl
github
google
handlebars
html-tools
htmljs
http
jquery
json
less
livedata
localstorage
logging
markdown
mongo-livedata
mongo
oauth-encryption
oauth
oauth1
oauth2
random
reactive-dict
reactive-var
reload-safetybelt
reload
session
sha
templating
tinytest
tracker
twitter
ui
underscore
weibo
xmlbuilder
```
