# Kartini Linux : A historical brief and design decision.

Last year (about 3 year ago), My brain came with the idea of building a linux distribution with a minimal, customizable, 
and lightweight approach.

This idea was marching my head when I was with my friend crossing the road on a middle rice field (around 17 February 2018). 
My distribution idea is influenced by many inspiring distros like Arch, Alpine, CRUX, KISS and Linux From Scratch.

Hence, Kartini came into existence. The name Kartini did not come from Indonesia women emancipation Hero instead my ex-friend
 last name.

## 3-years Stalemate

Sadly this project stalled almost 3 years and many technical specification changes since then, the reason is my college task
 is too overwhelming, lack research about linux distribution internals and of course the mood of those who hate my ideas.

This happened due to many bad decisions on writing my package manager to manage my distribution package and of course maintaining
 package consensus, in short broken flow to prioritize features I want to develop first.

Felt like a mistake to write my own package manager because there are a lot of build systems that help me get a job done and
 the worst is rewriting it to another language without clear feature specification.

From programming language selection until standard procedure for handling packages. The first plan i want write the package
 manager on Ruby, then the second with Go ,and the last with OCaml, The result after rewrite through many language I learn 
 something about language selection

- A software that is required to run on a low-level environment, such an embedded and system level thing, needs to be
  built into a static native binary which can save a lot of time than satisfying the dependencies due limited 
  space and dependencies that are harder to maintain in that level. Here is why I choose Go and OCaml because 
  it supports static native binary.

- Programming language ecosystem maturity, these factors had a significant impact on your productivity. Maturity of
  library and tooling give you cost-effective time saving due not reinvent many wheels on your program (except your wanna 
  to contribute to the ecosystem).


When rewriting in Go and OCaml, I start to adapt with the KISS package system standard and it begins to show good
 output. I got mvp but i realize this not enough, i still need additional mechanism to improving developer
  experience and my mistake is

- Standardization and flow specification of the software, this should be mature before you hand get dirty with code.
  My mistake is too many spec changes and result none.


- Clear purpose and consistency, this what made kartini meet stalemate and sleep about 3 years followed above
 complication.

I admit this can be considered bad practices of software engineering made by me. It requires good both hard skill
 and proper way to maintain productivity of yourself in work to endure an idea to become real.


## Resolution

On April 25 2021, I had done implementing half package manager specification (this heavily inspired by KISS package
 system) and being able to build minimal filesystems took a month to revive this idea back to my brain.

 - [The Package Consensus Repository](https://github.com/kartini-linux)
 - [The Package Manager Repository](https://github.com/52ml/kartini)

Package manager progress gave me a path to eagerly continuing my idea. 

Now, I am dealing with some bigger
 problems : what I want to distribute and how it form output. Of course, we need init, libc , kernel , boot, GUI and other major utility
  tools in our filesystem to distribute but the real problem is how it will look like. So the decision i took

- Init : Runit
- Libc : Glibc (this will be replace with musl + gcompat in future)
- Boot : Syslinux
- Utility : Busybox
- Package Manager: kartini
- GUI: IceWM with X server

This decision was based on a lightweight, minimal and customizable approach. I felt glibc is thing not lightweight
so i will replace it with musl + gcompact (in order to make it compatible with binary builded in glibc) in future,
because i still pursue how make this distribution usable, can be distribute without much obstacle and running without hussle 
in near time.

Until this day I'm still messing with basic standard build and its configuration, surely I'm really new to this and
 I hope I can fight till the end. 
  
This post will be updated as I continue to develop it, and need to learn how to
manage time properly both developing, rest time and college stuff.
