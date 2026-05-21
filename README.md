# Padloc

Padloc is a lightweight, browser-based password manager built with Polymer, RequireJS, and Gulp. It allows users to securely store and manage passwords locally in their browser.

## Features

- **Local Storage**: Passwords are stored securely in the browser using local storage.
- **Master Password**: Protect your data with a master password.
- **Category Management**: Organize passwords into categories.
- **Import/Export**: Easily import and export password data.
- **Customizable UI**: Built with Polymer components for modularity and customization.

## Tech Stack

- **Frontend**: Polymer, RequireJS
- **Build Tools**: Gulp
- **Testing**: QUnit
- **Dependencies**: Managed with npm and Bower

## Installation

### Prerequisites

Ensure the following are installed on your system:

- **Node.js** and **npm**
- **Bower** (install globally with `npm install -g bower`)
- **Gulp CLI** (optional, install with `npm install -g gulp-cli`)

### Steps

1. Clone the repository:

   ```bash
   git clone https://github.com/Akshit1025/padloc.git
   cd padloc
   ```

2. Install dependencies:

```bash
npm install
bower install
```

3. If Compass is not installed, run:

   ```bash
   gem install multi_json -v 1.15.0
   gem install ffi -v 1.15.5
   gem install compass
   ```

## Usage

### Run the App

Start a local static server from the project root:

```bash
python -m http.server 8080
```

Then open the app in your browser:

```text
http://localhost:8080
```

You can specify a different port if needed:

```bash
python -m http.server 3000
```

### Build Styles

Compile the Stylus files into CSS using the Gulp task:

```bash
gulp stylus
```

Use `gulp stylus --watch` to watch and recompile on file changes.

This generates the CSS files required by `index.html` and the Polymer components.

### Development Workflow

1. **Stylus Compilation**:
   - Compile `.styl` files into CSS:
     ```bash
     gulp stylus
     ```
   - Watch for changes and recompile automatically:
     ```bash
     gulp stylus --watch
     ```

2. **Testing**:
   - Run QUnit tests:
     ```bash
     gulp test
     ```

3. **Linting**:
   - Lint JavaScript and HTML files:
     ```bash
     gulp lint
     ```
   - Watch for changes and lint automatically:
     ```bash
     gulp lint --watch
     ```

4. **Deployment**:
   - Build and deploy the app to a specified folder:
     ```bash
     gulp deploy --dest <destination-folder>
     ```

## Testing

Unit tests are located in the `test/` directory. Open `test/runner.html` in your browser to run the tests.

## Project Structure

- `index.html`: Main entry point of the app
- `src/`: Application source code and Polymer components
  - `components/`: Modular UI components
- `lib/`: Shared libraries (e.g., `sjcl` for cryptography)
- `test/`: Unit tests and test runner
- `bower_components/`: Frontend dependencies
- `node_modules/`: Development dependencies

## Troubleshooting

### Blank Page in Browser

This usually indicates missing CSS files. Run:

```bash
bundle exec compass compile
```

### Stylus / Gulp Issues on Windows

If styles are not generated, ensure `node_modules` is installed and the Gulp dependencies are present:

```bash
npm install
gulp stylus
```

If you rely on a global `gulp` command and it's missing, install the Gulp CLI:

```bash
npm install -g gulp-cli
```

### Missing Dependencies

If `bower_components/` is empty, run:

```bash
bower install
```

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Contributing

Contributions are welcome! Feel free to submit issues or pull requests to improve the project.
