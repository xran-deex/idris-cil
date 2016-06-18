# idris-cil [![Build Status](https://travis-ci.org/bamboo/idris-cil.png?branch=master)](https://travis-ci.org/bamboo/idris-cil)

A Common Intermediate Language backend for [Idris](http://www.idris-lang.org/).

## Why

Because programmers targeting the CLR deserve a modern pure functional language with dependent types.

## Usage

Given a `Main.idr` file:

```idris
module Main

main : IO ()
main = putStrLn "Hello, Idris!"
```

Compile it to cil and execute it with mono:

```
idris --codegen cil Main.idr -o HelloWorld.exe \
  && mono HelloWorld.exe
```

The resulting assemblies can also be used with .NET or Unity.

## Building

It's important that the version of the Idris executable matches the version used to build idris-cil:

	git clone git@github.com:bamboo/idris-cil
	cd codegen
	stack install idris
	stack install

The runtime system is required for the FFI (and to run the tests):

	cd rts
	idris --install cil.ipkg

## Contributing

Issue reports and PRs are welcome.

Brought to you by @bamboo, @sangamon and [contributors](https://github.com/bamboo/idris-cil/graphs/contributors).


