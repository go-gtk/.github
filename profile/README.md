# go-gtk

[![License](https://img.shields.io/badge/license-BSD--3--Clause-blue.svg)](https://github.com/go-gtk/gtk4/blob/main/LICENSE)
[![Pure Go](https://img.shields.io/badge/pure%20Go-CGO%3D0-00ADD8?logo=go&logoColor=white)](https://github.com/go-gtk/gtk4)
[![Go Reference](https://pkg.go.dev/badge/github.com/go-gtk/gtk4.svg)](https://pkg.go.dev/github.com/go-gtk/gtk4)

**GTK4 from pure Go.**

A Go program that wants real Linux widgets has had one option: cgo, and with it
a C toolchain in every build, on every architecture, for every contributor.

There is another way. GTK is a C library with a stable ABI, and `dlopen` is a
system call. go-gtk loads libgtk-4 through purego and calls it directly, so
`CGO_ENABLED=0` holds all the way down and the binary still cross-compiles.

## What is here

**[gtk4](https://github.com/go-gtk/gtk4)** — GTK4 bound through purego:
widgets, windows, events and the main loop.

## Where it sits

This is the Linux third of the native-toolkit bridge
[go-widgets](https://github.com/go-widgets) paints through — the sibling of
[go-macos](https://github.com/go-macos)'s Objective-C runtime bridge and of
[go-mswin](https://github.com/go-mswin) on Windows. Going through the platform's
own toolkit rather than painting pixels is what buys the things a drawn widget
cannot have: the desktop's input methods, its accessibility tree, and its idea
of what a control looks like this year.

Part of the **Desktop & widgets** family of the
[pure-Go ecosystem](https://go-desktop.github.io/): no cgo, no shelling out to a
command-line tool in place of a library, built on six 64-bit architectures, 100%
statement coverage as a CI gate, BSD-3-Clause.
