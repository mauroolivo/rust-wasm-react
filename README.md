# Rust Wasm React Template

This repo is a starting point template to develop a react project backed with rust code embedded via WebAssembly.
Both, Rust and React code, can be changed and changes seen in the browser. 

## How to configure 

### Rust setup 
```sh
 $ cargo new react-wasm-react --lib   
```
- update [cargo.toml](https://github.com/mauroolivo/rust-wasm-react/blob/main/Cargo.toml)
- add [utils.rs](https://github.com/mauroolivo/rust-wasm-react/blob/main/src/utils.rs)
- update [lib.rs](https://github.com/mauroolivo/rust-wasm-react/blob/main/src/lib.rs)

The rust part is ready, now create the web assembly with
```sh
 $ wasm-pack build --target web
```
or equivalently:
```sh
 $ rustup target add wasm32-unknown-unknown
 $ cargo build --target wasm32-unknown-unknown --release
```
### React setup

Initialize a rect project inside the rust-wasm-react folder
```sh
 $ npx create-react-app www
```
in `www/package.json` add the wasm pkg dependency
```json
{
  "dependencies":
  {
    "rust-wasm-react": "file:../pkg"  
  }
}
```
"dependencies": {
"...",

}
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