# c-compiler-implementations

This is a list of reader implementations of the project from _[Writing a C Compiler](https://nostarch.com/writing-c-compiler)_, ~shamelessly ripped off from~ lovingly inspired by the list of [implementations of Lox from _Crafting Interpreters_](https://github.com/munificent/craftinginterpreters/wiki/Lox-Implementations). I hope this will be a useful resource for readers planning to complete the project in a lots of different languages.

See the [contributing](#contributing) section for details on how to add your implementation to the list. Incomplete, unpolished, and hacky implementations are welcome!

**Disclaimer: I haven't code reviewed these implementations. As with any untrusted code, please be cautious about running these on your own computer.**

# Contents

* [Contributing](#contributing)
* [Implementations](#implementations)
  * [C](#c)
  * [C++](#c-1)
  * [OCaml](#ocaml)
  * [Rust](#rust)

# Contributing

Please add your C compiler to this page if:

1. It's basically following the design in [_Writing a C Compiler_](https://nostarch.com/writing-c-compiler) (the book, not the [blog posts](https://norasandler.com/2017/11/29/Write-a-Compiler.html), which are quite different).
2. You've finished at least chapter 1.

Your compiler does **not** need to be complete, polished, or production-ready, and it does not need to follow the book exactly. Compilers that implement extra language features, target different processors or are organized into different passes are totally welcome.

Open a pull request to add your compiler to the list for the appropriate implementation language, in alphabetical order. If there isn't already a subheading for your implementation language, please go ahead and add one (make sure to add it to the the [table of contents](#contents) too!) If you don't have a Github account, you can [email me](mailto:nora@norasandler.com) and ask me to add it for you.

For projects hosted on Github, please use the following format:

 * [USERNAME/REPO](https://github.com/username/repo) - A few optional sentences about your project. E.g. if you've made different design decisions than the book suggests or implemented extra features, you can mention it here.

For projects hosted elsewhere, use this format:

 * [name of project](https://) - A few optional sentences about your project. E.g. if you've made different design decisions than the book suggests or implemented extra features, you can mention it here.

# Implementations

## C

## C++

* [Gnomeball/C-Compiler](https://github.com/Gnomeball/C-Compiler) - Implemented on Linux; only notable change from the intended design is the use of a byte code representation instead of an AST while parsing; so far only chapter one is 'complete', though it's extremely rough.

* [romainducrocq/wheelcc](https://github.com/romainducrocq/wheelcc) - C++ (>=17) implementation for Linux: with some builtin preprocessing, comprehensive error messages with source locations and more features to come! (Part 1, 2 and extra-credits done. Part 3 in progress.)

## OCaml

* [nlsandler/nqcc2](https://github.com/nlsandler/nqcc2) - This is the official reference implementation for the book!

## Rust

* [ianyourgod/batpu-c-compiler](https://github.com/ianyourgod/batpu-c-compiler) - Rust implementation for the [BATPU2](https://www.youtube.com/watch?v=3gBZHXqnleU), a CPU made for/in minecraft: uses the GCC preprocessor, and has absolutely terrible error messages. All parts finished. A few part 2 features are missing (floats, longs, unsigned), as the CPU does not support them.

* [neildanson/c_compiler](https://github.com/neildanson/c_compiler) - Rust implementation based entirely on the book, following x86-64. Verified working on WSL2 on Windows and MacOS. Work In progress.

* [ysono/compiler-c-sandler](https://github.com/ysono/compiler-c-sandler/) - Implementation details diverge from the book's instructions in various ways. The behavior is consistent with the way the book clamps down on undefined behaviors. Tested on Linux and Intel Mac. Work in progress.
