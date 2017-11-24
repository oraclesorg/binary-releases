# Binary releases of Parity client

## Why?

Sometimes we need to modify Parity client with quick fixes on our side.
E.g. with bug

## How?

A sample flow:
- Download source of Parity release on https://github.com/paritytech/parity/releases
- Unzip downloaded file to a folder
- Create a branch on `binary-releases` repo with version number, e.g., 1.8.3
- Run `git checkout 1.8.3`
- Add `.travis.yml` file

```
language: rust
rust:
  - 1.21.0
cache: cargo
script:
  - cargo build --release
```

- git add, commit, push
- Travis will start to build