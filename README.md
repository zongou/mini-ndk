# mini-ndk

Compiling android targeted binary is a pain on aarch64 linux and android, because ndk is not distributed on them, this repo show you how you can do that with ndk and llvm toolchain.

## How dose this work?

checkout [tests/test_toolchain.sh](tests/test_toolchain.sh)

## Setup instruction

### Get NDK

- [google](https://developer.android.google.com/ndk/downloads)
- [github](https://github.com/android/ndk/releases)

Then run:

```sh
## Unzip android ndk to somewhere
unzip <android_ndk_package>

## Get resouce from ndk
./mini-ndk setup <path_to_ndk_root>
```

### Get LLVM

- alpine:`apk add llvm lld`
- [zig](https://ziglang.org/download/):`export ZIG=<path_to_zig>`

- [static-clang](https://github.com/dzbarsky/static-clang/releases), [llvm-project](https://github.com/llvm/llvm-project/releases), [llvmbox](https://github.com/rsms/llvmbox/releases) or other llvm toolchain : `export PATH=${PATH}:<path_to_llvm_bin>`

### Test

```sh
./bin/aarch64-linux-android21-clang tests/hello.c
./bin/aarch64-linux-android21-clang++ tests/hello.cpp
```

## Relavent links

- [Assembling a Complete Toolchain](https://clang.llvm.org/docs/Toolchain.html)
- [llvm-cross-toolchains](https://github.com/shengyun-zhou/llvm-cross-toolchains)
