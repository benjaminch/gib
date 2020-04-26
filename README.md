# `gib` - A `.gitignore` bootstrapper for projects using `git`

## Installation
TODO

## Usage
### Create `.gitignore` at current directory (if it doesn't exist)
```bash
$ gib [<template>...] 
```

If a `.gitignore` file already exists at that location, `gib` will do nothing. **\[WIP\]** If you want to extend an existing file instead, use the `-a|--append` flag. If you want to overwrite it, use `-r|--replace`. Check the examples below.

### Create `.gitignore` at other directory
```bash
$ gib [<template>...] [-o|--output] [<path>]
```

### Get list of available templates
```bash
$ gib [-l|--list]
```

### Print result of specified templates to `stdout` only
```bash
$ gib [<template>...] [-s|--show]
```

## Examples
### Output `.gitignore` file for Go and Rust
```bash
$ gib go rust
```
#### `.gitignore`
```
###############
#   Go
###############
# Binaries for programs and plugins
*.exe
*.exe~
*.dll
*.so
*.dylib

# Test binary, built with `go test -c`
*.test

# Output of the go coverage tool, specifically when used with LiteIDE
*.out

# Dependency directories (remove the comment below to include it)
# vendor/

###############
#   Rust
###############
# Generated by Cargo
# will have compiled files and executables
/target/

# Remove Cargo.lock from gitignore if creating an executable, leave it for libraries
# More information here https://doc.rust-lang.org/cargo/guide/cargo-toml-vs-cargo-lock.html
Cargo.lock

# These are backup files generated by rustfmt
**/*.rs.bk
```
## Pending changes
- [ ] Add `append` and `replace` flags for working with existing `.gitignore` files.
- [ ] Replace `.gitignore` template loading with [`lazy_static`](https://docs.rs/lazy_static/) or [`phf`](https://github.com/sfackler/rust-phf)?