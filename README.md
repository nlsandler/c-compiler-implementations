# c-compiler-implementations

This is a list of reader implementations of the project from _[Writing a C Compiler](https://nostarch.com/writing-c-compiler)_, ~shamelessly ripped off from~ lovingly inspired by the list of [implementations of Lox from _Crafting Interpreters_](https://github.com/munificent/craftinginterpreters/wiki/Lox-Implementations). I hope this will be a useful resource for readers planning to complete the project in a lots of different languages.

See the [contributing](#contributing) section for details on how to add your implementation to the list. Incomplete, unpolished, and hacky implementations are welcome!

**Disclaimer: I haven't code reviewed these implementations. As with any untrusted code, please be cautious about running these on your own computer.**

# Contents

* [Contributing](#contributing)
* [Implementations](#implementations)
  * [Ada](#ada)
  * [C](#c)
  * [C++](#c-1)
  * [Haskell](#haskell)
  * [Java](#java)
  * [OCaml](#ocaml)
  * [Perl](#perl)
  * [Python](#python)
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

## Ada

* [JeremyGrosser/wacc](https://github.com/JeremyGrosser/wacc) - Handwritten lexer, using record types with discriminants to model ASDL structures.

## C

* [LesleyLai/mcc](https://github.com/LesleyLai/mcc) - A C23 implementation. While loosely following the book, I also consulted other resources, and this implementation has notable deviations, including a handwritten lexer, name resolution within the parser, and a slightly different IR design.

## C++

* [Gnomeball/C-Compiler](https://github.com/Gnomeball/C-Compiler) - Implemented on Linux; only notable change from the intended design is the use of a byte code representation instead of an AST while parsing; so far only chapter one is 'complete', though it's extremely rough.

* [romainducrocq/wheelcc](https://github.com/romainducrocq/wheelcc) - C++ (>=17) implementation for Linux: with some builtin preprocessing, comprehensive error messages with source locations and more features to come! (Part 1, 2 and extra-credits done. Part 3 in progress.)

## Haskell

* [0xpantera/halcyon](https://github.com/0xpantera/halcyon) - Uses parser combinators for lexer and parser instead of regular expressions. Work in progress. Check out the project README for details on current functionality and progress.

## Java

* [dplassgit/adventofcompilers](https://github.com/dplassgit/adventofcompilers) - Java 21 implementation. Hand-rolled lexer (no regexp). Pretty faithful to the book, except with more meaningful names to disambiguate AST nodes from Tacky nodes from Assembly nodes. Complete through Chapter 11 (not including extra credits.)

## OCaml

* [nlsandler/nqcc2](https://github.com/nlsandler/nqcc2) - This is the official reference implementation for the book!

* [lc](https://git.sr.ht/~laumann/lc) - Work in progress, Part I
  completed, implements extra credit features (Duff's
  device!). Follows the book fairly closely. Has no dependencies
  beyond the OCaml stdlib.

## Perl

* [sir-galahad/adcc](https://github.com/sir-galahad/adcc) - C compiler in Perl, for Linux seemed like a good idea, Perl hashes make it quick to build complex data structures.

## Python

* [gh-nate/wacc](https://github.com/gh-nate/wacc) - Work in progress. Did not expect to write so many tests so progress will be slow as I also explore organizing and adding tests based on what's in the book.

## Rust

* [ceronman/writing-a-c-compiler](https://github.com/ceronman/writing-a-c-compiler) - Work in progress, I have implemented up to chapter 12 including all extra-credit. Only macOS supported for now. I push updates almost every day.

* [ianyourgod/batpu-c-compiler](https://github.com/ianyourgod/batpu-c-compiler) - Rust implementation for the [BATPU2](https://www.youtube.com/watch?v=3gBZHXqnleU), a CPU made for/in minecraft: uses the GCC preprocessor, and has absolutely terrible error messages. All parts finished. A few part 2 features are missing (floats, longs, unsigned), as the CPU does not support them.

* [neildanson/c_compiler](https://github.com/neildanson/c_compiler) - Rust implementation based entirely on the book, following x86-64. Verified working on WSL2 on Windows and MacOS. Work In progress.

* [ysono/compiler-c-sandler](https://github.com/ysono/compiler-c-sandler/) - Implementation details diverge from the book's instructions in various ways. The behavior is consistent with the way the book clamps down on undefined behaviors. Tested on Linux and Intel Mac. Work in progress.
