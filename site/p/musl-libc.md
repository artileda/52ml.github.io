# Musl-libc : An alternative C Library.

C Library (**libc**, for short) provides standard library functions such as maths,
, input/output, memory, and task related to operating system internal on C programming language. 

In my previous article about Kartini Linux I mentioning GLibc, GLibc is short for GNU Lib C is 
an implementation of the C standard library started by GNU Project and the most widely used C Library.

There many various implementations other than GLibc:
- [Musl-libc](http://musl.libc.org/)
- [Dietlibc](https://www.fefe.de/dietlibc/)
- [uClibC](https://uclibc-ng.org/)
- [Newlib](http://www.sourceware.org/newlib/)

Why that many implementations of C Library ? the answer is a target of compilation, some C Library are
intended is focus on an embedded program, wide-range CPU architecture support,a smaller binary program, supporting a Linux system, etc.

## What is Musl - Libc exactly ?

According to it [official site](http://musl.libc.org/), **musl** is an implementation of the C standard library built on top of the Linux system call API, including interfaces defined in the base language standard, POSIX, and widely agreed-upon extensions.

Musl tend to be simple, lightweight and ease to deploy despite it corretness to standard.

You can download pre-build binary toolchain to ease do cross/native musl compilation, [musl.cc](https://musl.cc/).

## My story with musl

The first time I encounter with Musl when I am using Alpine Linux after migrating from Arch Linux as my distro for daily basis usage. 
Sometimes I meet an error when an encounter with AppImage and other single binary due they find symbolic
function provided by GLibc. This can be mitigated by compiling its source directly against Musl-Libc as it C Library. 

Of course there another solution for this occassion, Musl is not fully compatible with
ABI provided by Glibc, to overcome this Adelie Linux make a library bridging these incompatibilities between Glibc and Musl.
So **gcompat** come into existence. Unfortunately, I have not tried it.

C Library had a crucial role in distribution due it works as a building block alongside kernel and operating system utilities. Without it
 the program could not run well, even can crash whole distribution because the whole program in distro linking against it (except static linked binary executable).

