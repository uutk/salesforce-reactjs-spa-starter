# Salesforce ReactJS SPA Starter

A template project to create ReactJS-based single page application on Salesforce, with automatic build script (Gulp.js)

## Setup

Make sure you are installing Node.js 0.10.x or later.

```
$ node --version
```

Then execute following commands in project directory root:

```
$ npm install
$ bower install
```

If you have not installed the `gulp` command yet, install it by following command :

```
$ npm install -g gulp
```

## Build Files

Run the `gulp` command to build runnable codes from source code :

```
$ gulp
```

for automatic building you can specify `watch` task option for gulp

```
$ gulp watch
```

## Preview

Start web server by following command :

```
$ gulp dev
```

Then access to `http://localhost:8000`.

The command watches source code update and builds automatically.


## Test

Run unit tests

```
$ gulp test
```

For automatic test execution: (update watch)

```
$ gulp test:watch
```


## Deploy (Salesforce)

With username and password (may include security token) as environment variables to connect to Salesforce,
execute `gulp deploy` command :

```
$ SF_USERNAME=yourname@example.org SF_PASSWORD=password gulp deploy
```
or prepare `.env` file in `KEY=VALUE` format:

```
SF_USERNAME=yourname@example.org
SF_PASSWORD=password
```

Then execute `gulp deploy` using `foreman` :

```
$ nf run gulp deploy
```

The `nf` command can be installed by `npm install -g foreman`.


## Project Directory Structure

```
├── app                    # Source code directory
│   ├── assets               # HTML, images, fonts, or other static files
│   │   ├── index.html         # Entry point HTML
│   │   ├── ...
│   │
│   ├── scripts              # Script files that can be compiled to JS
│   │   ├── components         # Scripts for ReactJS components 
│   │   │   ├── bar.jsx          # ES6 JS (.js or .jsx), which can include JSX
│   │   │   ├── baz.cjsx         # CoffeeScript (.cjsx or .coffee), which can include JSX
│   │   │   ├── foo.coffee
│   │   │   ├── foo.coffee
│   │   │   ├── ...
│   │   │ 
│   │   ├── main.js            # Entry point of app script
│   │   ├── ...
│   │
│   ├── styles               # Stylesheet files to be compiled to CSS
│   │   ├── components         # Stylesheets for ReactJS components
│   │   │   ├── bar.less
│   │   │   ├── baz.less
│   │   │   ├── foo.less
│   │   │   ├── ...
│   │   │ 
│   │   ├── main.less          # Entry point of CSS
│   │   ├── ...
│   │
│   └── templates            # ReactJS Templates
│       └── components         
│           ├── foo.rt           # matching to app/scripts/components/foo.coffee
│           ├── root.rt          # matching to app/scripts/components/root.js
│           ├── ...
│
├── build                  # Directory which includes all built files generated by gulp script
│   ├── app
│   │   ├── index.html
│   │   ├── scripts
│   │   ├── styles
│   │   ├── ...
│   │
│   └── test
│       ├── ...
│
├── bower.json             # Depending library setting
├── gulpfile.coffee        # Gulp build script
├── package.json           # Project settting
│
├── src                    # Force.com project
│   ├── package.xml
│   ├── pages
│   │   ├── MyAppPage.page
│   │   └── MyAppPage.page-meta.xml
│   └── staticresources
│       ├── MyApp.resource     # Zip file containing built static files (generated by gulp)
│       ├── MyApp.resource-meta.xml
│       ├── MyAppLib.resource  # Zip file containing bower libs (generated by gulp)
│       └── MyAppLib.resource-meta.xml
│
└── test                   # Test code directory
    ├── e2e                  # End-to-End test
    │   ├── app001.test.js
    │   ├── ...
    │
    └── unit                 # Unit test
        ├── components          # ReactJS component unit test
        │   ├── bar.test.js
        │   ├── baz.test.js
        │   ├── foo.test.js
        │   ├── ...
        ├── ...
```
