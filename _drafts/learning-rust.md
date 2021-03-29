---
layout: post
title: 'I am learning Rust'
tags:
  - rust
  - changelog
  - conventional commits
---

I am using [gitui](https://github.com/extrawurst/gitui) as my primary graphical git tool and I had some issues with it. First the `external Editor` Feature didn't work, now pushing to the upsteam branch. So I decided to check the sources. It's an open-source project, so why not. That was my first encounter with Rust.

Throughout the years I learned a few programming languages like `python`, `java`, `c#` so I had no problem reading it. Understanding what the code actually did was something completely different. So I tried to "fix" a bug tagged as a `good first issue`. That is where the journey began.

A few things to mention:
- I didn't fix the bug 😅 My PR wasn't fully merged. But I decided to give it a try.
- At this point I didn't read ["the book"](https://doc.rust-lang.org/book/) or anything else about Rust. I just started. Hands on experience.

I decided to create a changelog generator based on both conventional commits and non-conventional commits[^1].

This will be an ongoing series of posts with my current learnings about Rust and what I intend to do next.

Check the current status of the project over at [ser-drephs/changelog](https://github.com/ser-drephs/changelog).

## Table of contents <!-- omit in toc -->
- [What is this post about?](#what-is-this-post-about)
- [Setup](#setup)
- [Start the project](#start-the-project)
- [Run and debug](#run-and-debug)

## What is this post about?

This post is about how I started my first ever Rust project. My experience on how to setup my dev machine and why I use which "IDE".

## Setup

Setting up my computer for Rust development was pretty easy. Head over to [Rust Lang Install](https://www.rust-lang.org/tools/install) to download `rustup`. During the installation it was required to download some Visual C++ Redistributables. I don't remember which, but the setup guides you through this. After that you are already set up.

I use [Visual Studio Code](https://code.visualstudio.com/) with the [Rust Extension](https://marketplace.visualstudio.com/items?itemName=rust-lang.rust) for development. The [C/C++ Extension](https://marketplace.visualstudio.com/items?itemName=ms-vscode.cpptools) is also required for debugging.

## Start the project

Rust uses so called "crates". [Crates](https://crates.io/) are packages which you can use in your application. Cargo is the package manager for Rust.

To start a new Rust project just open a shell and type `cargo new <name>` ex. `cargo new changelog`. Cargo then generates a project stub for your new project.

```shell
D:\sources> cargo new changelog
     Created binary (application) `changelog` package
D:\sources> ls .\changelog\

    Directory: D:\sources\changelog

Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d----          26.03.2021    09:08                src
-a---          26.03.2021    09:08              8 .gitignore
-a---          26.03.2021    09:08            226 Cargo.toml
```

## Run and debug

To build the project simply run `cargo build` in your shell or use VSCode to build it.

It's also possible to debug the application within VSCode. Simply set a breakpoint and hit <kbd>F5</kbd>. I have two debug configurations for this project, because I also wanted to debug my unit tests. My `launch.json` look like this:

```json
{
    // Use IntelliSense to learn about possible attributes.
    // Hover to view descriptions of existing attributes.
    // For more information, visit: https://go.microsoft.com/fwlink/?linkid=830387
    "version": "0.2.0",
    "configurations": [
        {
            "type": "lldb",
            "request": "launch",
            "name": "Debug executable 'changelog'",
            "cargo": {
                "args": [
                    "build",
                    "--bin=changelog",
                    "--package=changelog"
                ],
                "filter": {
                    "name": "changelog",
                    "kind": "bin"
                }
            },
            "args": [],
            "cwd": "${workspaceFolder}"
        },
        {
            "type": "lldb",
            "request": "launch",
            "name": "Debug unit tests in executable 'changelog'",
            "cargo": {
                "args": [
                    "test",
                    "--no-run",
                    "--bin=changelog",
                    "--package=changelog"
                ],
                "filter": {
                    "name": "changelog",
                    "kind": "bin"
                }
            },
            "args": [],
            "cwd": "${workspaceFolder}"
        }
    ]
}
```

Now that everything is set up: Let's go!

{: data-content="footnotes"}

[^1]: With non-conventional commits I mean just any commit without a specific structure. The commits are just sorted by commit time.