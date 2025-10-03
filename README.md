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
  * [Cython](#cython)
  * [Go](#go)
  * [Haskell](#haskell)
  * [Jai](#jai)
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

* [romainducrocq/wheelcc](https://github.com/romainducrocq/wheelcc) - An ISO C17 implementation for Linux and MacOS that depends only on Glibc, POSIX and bash. It covers 100% of the book (parts 1-3 + extra-credits, passes all the tests), with additions such as a handwritten lexer, support for includes and comprehensive error messages. The design follows the book, but many details have been changed and some compiler stages were combined. The project also builds in C++.

## C++

* [Gnomeball/C-Compiler](https://github.com/Gnomeball/C-Compiler) - Implemented on Linux; only notable change from the intended design is the use of a byte code representation instead of an AST while parsing; so far only chapter one is 'complete', though it's extremely rough.

* [Sh0g0-1758/scarlet](https://github.com/Sh0g0-1758/scarlet) - C++ (>=20) implementation featuring multiline error recovery and CI-verified builds. Completed Part 1 with all extra credits. Implementation largely follows the book with deviations in semantic analysis stage. Parts 2/3 in active development targeting x86_64 (Linux/macOS). Roadmap includes extensive static analysis optimizations and a future machine learning framework. Built with CMake and tested across GCC/Clang.

* [alexkowalenko/axc](https://github.com/alexkowalenko/axc) - Written in verbose C++23. Completed up to chapter 9 for the X86_64 architecture. Tested on MacOS and FreeBSD.

## Cython

* [romainducrocq/cube](https://github.com/romainducrocq/cube) - An early version of [romainducrocq/wheelcc](https://github.com/romainducrocq/wheelcc) that implements chapters 1 to 13, before switching the compiler implementation to C/C++. It will no longer receive updates.

## Go

* [JusticeProject/Go-C-Compiler](https://github.com/JusticeProject/Go-C-Compiler) - Following the book closely. Runs on Linux. Finished Chapter 9. No extra credit features implemented (yet).

## Haskell

* [0xpantera/halcyon](https://github.com/0xpantera/halcyon) - Uses parser combinators for lexer and parser instead of regular expressions. Work in progress. Check out the project README for details on current functionality and progress.

## Jai

* [amantuladhar/jai-c-compiler](https://github.com/amantuladhar/jai-c-compiler) - [WIP Ch 8] A work-in-progress implementation of a compiler in Jai. The project is not complete but implements extra credit features from the book. Error reporting is handled as a separate concern, allowing it to point to the exact location of errors in the source file. Output in different stage are written to support polymorphic writers to make output verification easier.

## Java

* [dplassgit/adventofcompilers](https://github.com/dplassgit/adventofcompilers) - Java 21 implementation. Hand-rolled lexer (no regexp). Pretty faithful to the book, except with more meaningful names to disambiguate AST nodes from Tacky nodes from Assembly nodes. Complete through Chapter 11 (not including extra credits.)

* [mikeyreilly/mcc](https://github.com/mikeyreilly/mcc) - Java implementation with heavy use of pattern matching. Aiming to do extra credit stuff after I finish Chapter 20.

## OCaml

* [nlsandler/nqcc2](https://github.com/nlsandler/nqcc2) - This is the official reference implementation for the book!

* [lc](https://git.sr.ht/~laumann/lc) - Work in progress, Part I
  completed, implements extra credit features (Duff's
  device!). Follows the book fairly closely. Has no dependencies
  beyond the OCaml stdlib.

* [Maruncho/C-Toy-Compiler](https://github.com/Maruncho/C-Toy-Compiler) - [WIP] Will cover all chapters and all extra credit features, plus some extra stuff I find interesting.
  My implementation differs mainly in its type checking, which is performed during parsing rather than in a separate pass, with the intent of adding typedef support in the future.

## Perl

* [sir-galahad/adcc](https://github.com/sir-galahad/adcc) - C compiler in Perl, for Linux seemed like a good idea, Perl hashes make it quick to build complex data structures.

## Python

* [gh-nate/wacc](https://github.com/gh-nate/wacc) - Part I completed without extra credits. Verification relies on test suite mentioned in the book.

## Rust

* [ceronman/writing-a-c-compiler](https://github.com/ceronman/writing-a-c-compiler) - Work in progress, I have implemented up to chapter 12 including all extra-credit. Only macOS supported for now. I push updates almost every day.

* [ianyourgod/batpu-c-compiler](https://github.com/ianyourgod/batpu-c-compiler) - Rust implementation for the [BATPU2](https://www.youtube.com/watch?v=3gBZHXqnleU), a CPU made for/in minecraft: uses the GCC preprocessor, and has absolutely terrible error messages. All parts finished. A few part 2 features are missing (floats, longs, unsigned), as the CPU does not support them.

* [neildanson/c_compiler](https://github.com/neildanson/c_compiler) - Rust implementation based entirely on the book, following x86-64. Verified working on WSL2 on Windows and MacOS. Work In progress.

* [ysono/compiler-c-sandler](https://github.com/ysono/compiler-c-sandler/) - Implementation details diverge from the book's instructions in various ways. The behavior is consistent with the way the book clamps down on undefined behaviors. Tested on Linux and Intel Mac. Work in progress.

* [asibahi/trjm](https://github.com/asibahi/trjm/) - Lexer and Parser written using parser combinator library `nom` and `nom-language`, but otherwise faithful to the book. As of Mar 16 it is up to chapter 13 (doubles), including extra features.

* [oddsoc/EdgehammerC](https://github.com/oddsoc/EdgehammerC/) - An in-development implementation supporting all features through chapter 11 (including extra-credit), with commits corresponding to each completed chapter. It closely follows *Writing a C Compiler*, with some deviations in implementation details.

* [rlivings39/learning-compilers](https://github.com/rlivings39/learning-compilers) - In-progress implementation that is my first introduction to Rust as well. Mostly follows the book. I added source location tracking to give good error messages in the lexer and parser. Contains my original implementation in TypeScript.

## Zig

* [asibahi/paella](https://github.com/asibahi/paella) - Straightforward implementation in Zig 0.14.0, with some ideas from the Zig compiler itself. Currently halfway to chapter 5 (variables).
