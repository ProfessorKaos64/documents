<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
**Table of Contents**  *generated with [DocToc](https://github.com/thlorenz/doctoc)*

- [Cmake](#cmake)
- [Quick tips](#quick-tips)
- [Cmake vs Make](#cmake-vs-make)
- [Simple example of setting and using an option in CMakeLists.txt](#simple-example-of-setting-and-using-an-option-in-cmakeliststxt)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

# Cmake
* [Cmake documentation](https://cmake.org/documentation/)
* [Cmake official Wiki](https://cmake.org/Wiki/CMake)
* [Getting started with cmake](http://mathnathan.com/2010/07/getting-started-with-cmake/)
* [Cmake - An introduction](http://www.cs.swarthmore.edu/~adanner/tips/cmake.php)
* [Useful variables](https://cmake.org/Wiki/CMake_Useful_Variables#Prefixes.2C_Suffixes_.28Postfixes.29.2C_and_Extensions)

# Quick tips

Check all cached [CMake](http://linux.die.net/man/1/cmake) variable options:

In the root folder of the project:
```
cmake -LAH
```

# Cmake vs Make
* [Cmake vs Make (Perpetual Enigma)](http://prateekvjoshi.com/2014/02/01/cmake-vs-make/)

# Simple example of setting and using an option in CMakeLists.txt

```
option(USE_CLANG "build application with clang" OFF) # OFF is the default
```

Then, wrap the clang-compiler settings in if()s:

```
if(USE_CLANG)
    SET (...)
    ....
endif(USE_CLANG)
```
