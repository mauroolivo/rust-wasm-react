# Rust Wasm React Template

This repository provides a template for developing React applications powered by Rust code compiled to WebAssembly (Wasm). It enables seamless integration between high-performance Rust logic and a modern React frontend, allowing for rapid development and live updates in the browser.

## Overview

This template demonstrates how to:
- Set up a Rust library for WebAssembly compilation
- Integrate the generated Wasm package into a React application
- Enable hot-reloading for both Rust and React code

## Prerequisites

- [Rust](https://www.rust-lang.org/tools/install) (with `wasm-pack` and `rustup`)
- [Node.js](https://nodejs.org/) and npm

## Getting Started

### 1. Rust Setup

Create a new Rust library project:

```sh
cargo new react-wasm-react --lib
```

Update the following files as needed:
- [`Cargo.toml`](https://github.com/mauroolivo/rust-wasm-react/blob/main/Cargo.toml)
- [`src/utils.rs`](https://github.com/mauroolivo/rust-wasm-react/blob/main/src/utils.rs)
- [`src/lib.rs`](https://github.com/mauroolivo/rust-wasm-react/blob/main/src/lib.rs)

Build the WebAssembly package using one of the following methods:

```sh
wasm-pack build --target web
```

or

```sh
rustup target add wasm32-unknown-unknown
cargo build --target wasm32-unknown-unknown --release
```

### 2. React Setup

Initialize a React project inside the `rust-wasm-react` folder:

```sh
npx create-react-app www
```

Add the generated Wasm package as a dependency in `www/package.json`:

```
"rust-wasm-react": "file:../pkg"
```

Install dependencies:

```sh
cd www
npm install
```

Update [`App.js`](https://github.com/mauroolivo/rust-wasm-react/blob/main/www/src/App.js) to initialize the Wasm library and call the exported Rust functions (e.g., `greet`).

### 3. Running the Application

Start the React development server:

```sh
npm start
```

The application will be available at `http://localhost:3000`.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Acknowledgements

- [Rust](https://www.rust-lang.org/)
- [wasm-pack](https://rustwasm.github.io/wasm-pack/)
- [React](https://react.dev/)

---

Maintained by [mauroolivo](https://github.com/mauroolivo) and contributors.
