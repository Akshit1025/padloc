# Padloc

Padloc is a minimal password manager app built with Polymer, RequireJS, Grunt, and Compass.

## What this repo is

This project is an older front-end web app. It uses:

- `node` and `npm` for the development server and build tooling
- `bower` for browser dependencies
- `grunt` for watch/build tasks
- `compass` for compiling SCSS into CSS
- `connect` for serving the app locally

## Requirements

Install these before running the app:

- Node.js and npm
- Bower
- Ruby 2.7.x with DevKit/MSYS2 on Windows
- Compass Ruby gem

## Install

From the project root:

```powershell
npm install
bower install
bundle install
```

If Bower is not installed yet:

```powershell
npm install -g bower
```

If Compass is not installed yet, use RubyGems:

```powershell
gem install multi_json -v 1.15.0
gem install ffi -v 1.15.5
gem install compass
```

## Run the app

Start a local static server:

```powershell
node server.js
```

Then open:

```text
http://localhost:8080
```

You can also specify a different folder or port:

```powershell
node server.js . 3000
```

## Build the styles

This app needs generated CSS files from the SCSS sources in `src/`.

Run:

```powershell
bundle exec compass compile
```

That generates the CSS files required by `index.html` and the Polymer components.

If `grunt-contrib-compass` shows a Windows warning such as `spawn EINVAL`, skip Grunt and use the `bundle exec compass compile` command above.

## Development workflow

In one terminal:

```powershell
npx grunt
```

In another terminal:

```powershell
node server.js
```

The default Grunt task starts `watch`; file changes then trigger Compass and QUnit.

## Important files

- `index.html` - app entry point
- `server.js` - local static server
- `Gruntfile.js` - build and watch tasks
- `config.js` - RequireJS configuration
- `src/` - app source code, styles, and Polymer components
- `lib/` - shared libraries, including `sjcl`
- `test/` - test runner and unit tests

## Troubleshooting

### Blank page in the browser

Usually means one of the generated CSS files is missing. Run:

```powershell
bundle exec compass compile
```

### Compass installation fails on Windows

Use Ruby 2.7.x with DevKit/MSYS2. Older front-end build tools like Compass often do not work well with Ruby 3.x.

If `gem install compass` fails with an `ffi` version error on Ruby 2.7, install the compatible `ffi` gem first:

```powershell
gem install multi_json -v 1.15.0
gem install ffi -v 1.15.5
gem install compass
```

If the error mentions `multi_json` instead, install it explicitly first:

```powershell
gem install multi_json -v 1.15.0
gem install ffi -v 1.15.5
gem install compass
```

### Missing browser dependencies

If files under `bower_components/` are missing, run:

```powershell
bower install
```

## App overview

Padloc is a password manager for storing and managing records locally in the browser. The UI starts with a master password screen and then lets the user lock, unlock, and manage records inside the app.
