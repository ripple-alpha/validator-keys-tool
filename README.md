# validator-keys-tool

Ripple Alpha validator key generation tool

## Table of contents

* [Dependencies](#dependencies)
  * [Ripple Alpha inclusion](#ripple-alpha-inclusion)
  * [Other dependencies](#other-dependencies)
* [Build and run](#build-and-run)
* [Guide](#guide)

## Dependencies

### Ripple Alpha inclusion

This project depends on the [ripple-alpha-core](https://github.com/ripple-alpha/ripple-alpha-core) repository for core signing functionality. If you have built and installed ripple-alpha-core, you can point this project at your installation using `CMAKE_PREFIX_PATH` (if you have installed in a standard system search path, this is not needed), e.g.:

```
$ cmake -DCMAKE_BUILD_TYPE=Release -DCMAKE_PREFIX_PATH=/path/to/ripple-alpha-core/installation/root ../..
```

Alternatively, if you do not have a local installation of ripple-alpha-core development files that you want to use, then this project will fetch an appropriate version of the source code using CMake's FetchContent.

### Other dependencies

* C++14 or greater
* [Boost](http://www.boost.org/) - 1.70+ required
* [OpenSSL](https://www.openssl.org/) 
* [cmake](https://cmake.org) - 3.11+ required

## Build and run

For linux and other unix-like OSes, run the following commands (see note above about adding `CMAKE_PREFIX_PATH` as needed):

```
$ cd ${YOUR_VALIDATOR_KEYS_TOOL_DIRECTORY}
$ mkdir -p build/gcc.debug
$ cd build/gcc.debug
$ cmake -DCMAKE_BUILD_TYPE=Release ../..
$ cmake --build .
$ ./validator-keys
```

For 64-bit Windows, open a MSBuild Command Prompt for Visual Studio
and run the following commands:

```
> cd %YOUR_VALIDATOR_KEYS_TOOL_DIRECTORY%
> mkdir build
> cd build
> cmake -G"Visual Studio 15 2017 Win64" ..
> cmake --build . --config Release
> .\Release\validator-keys.exe
```

32-bit Windows builds are not supported.

## Guide

[Validator Keys Tool Guide](doc/validator-keys-tool-guide.md)