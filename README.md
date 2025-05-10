# Rust Wasm React Template

This repo is a starting point template to develop a React project backed with Rust code embedded via Web Assembly.
Both, Rust and React code, can be changed and changes seen in the browser. 

## How to configure 

### Rust setup 
```sh
 $ cargo new react-wasm-react --lib   
```
- update [cargo.toml](https://github.com/mauroolivo/rust-wasm-react/blob/main/Cargo.toml)
- add [utils.rs](https://github.com/mauroolivo/rust-wasm-react/blob/main/src/utils.rs)
- update [lib.rs](https://github.com/mauroolivo/rust-wasm-react/blob/main/src/lib.rs)

The Rust part is ready, now create the Web Assembly with
```sh
 $ wasm-pack build --target web
```
or equivalently:
```sh
 $ rustup target add wasm32-unknown-unknown
 $ cargo build --target wasm32-unknown-unknown --release
```
### React setup

Initialize the Rect project inside the rust-wasm-react folder
```sh
 $ npx create-react-app www
```
in `www/package.json` add the wasm pkg dependency
```
"rust-wasm-react": "file:../pkg"  
```

to install the new dependency
```shell
 $ cd www
 $ npm install
```
- update [App.js](https://github.com/mauroolivo/rust-wasm-react/blob/main/www/src/App.js) to initialize the `wasm` library and call the `greet` function.

Finally launch the application 
```shell
 $ npm start
```