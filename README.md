# Build using cargo of rust

## Summary

Rustのビルドツール兼パッケージマネージャの`cargo`を使ってソースをビルドする.  

## Text

### Check version

```
$ cargo --version
```

### Create new cargo project

`cargo`で新しいプロジェクトを作成する.  

- ディレクトリがない状態から新規で作成

```
$ cargo new cargo_build --bin
$ cd cargo_build
```

- 作成済みのディレクトリなどを初期化する形で作成

```
$ mkdir cargo_build
$ cd cargo_build
$ cargo init
```

生成されたプロジェクトの内容は下記の通り.  

```
$ ls cargo_build
Cargo.toml	src
```

### Build cargo project

プロジェクトをビルドする.  

```
$ cargo build
   Compiling cargo_build v0.1.0 (/Users/takeshi/work/rust_src/cargo_build)
    Finished dev [unoptimized + debuginfo] target(s) in 2.71s
```

ビルド後の状態.  

```
$ ls cargo_build
Cargo.lock  Cargo.toml   src/    target/
```

### Run binary

ビルドされたソースを実行する.  

```
$ cargo run
    Finished dev [unoptimized + debuginfo] target(s) in 0.00s
     Running `target/debug/cargo_build`
Hello, world!
```

ファイル出力なしでビルドすることもできる.  
実行に至らないまでも, コードをチェックしたい場合はこちらを使うと良い.  

```
$ cargo check
    Checking cargo_build v0.1.0 (/Users/takeshi/work/rust_src/cargo_build)
    Finished dev [unoptimized + debuginfo] target(s) in 0.09s
```

## Extra

### How to release build

`cargo`を使って, Rustソースのリリースビルドを行うときは下記のコマンドで実施.  

```
$ cargo build --release
```

## Reference material
- https://doc.rust-jp.rs/book/second-edition/ch01-03-hello-cargo.html

