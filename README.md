# mini-ndk

Compiling android targeted biarny is a pain on aarch64 linux and android, because ndk is not distributed on them, this repo show you how you can do that with ndk and llvm toolchain.

## Setup instruction

Download these required resources:

- [zig](https://ziglang.org/download/)
- ndk from [google site](https://developer.android.google.com/ndk/downloads) or [github release](https://github.com/android/ndk/releases)

Then run:

```sh
## Unzip android ndk
unzip <android_ndk_package>

## Setup
./mini-ndk setup <ndk_home>
cp <path/to/zig> ./bin/

## Run test
./mini-ndk test
```

## Extra

This tool is not only limited to be used with zig. you can replace zig with other llvm toolchain, you will need to modify <mini-ndk/bin/wrapper>

for example to use llvmbox as toolchain

```sh
## open <path/to/mini-ndk/bin/wrapper>
## replace BIN=${BIN_DIR}/zig with BIN=${BIN_DIR}/clang

## Copy or link toolchain
cp <path/to/llvmbox>/bin/clang bin/clang
cp <path/to/llvmbox>/bin/ld.lld bin/ld.lld

## Run test
./mini-ndk test
```

## Relavent links

- [Assembling a Complete Toolchain](https://clang.llvm.org/docs/Toolchain.html)

- [llvm-project](https://github.com/llvm/llvm-project)
- [llvmbox](https://github.com/rsms/llvmbox)
- [llvm-cross-toolchains](https://github.com/shengyun-zhou/llvm-cross-toolchains)
- [dzbarsky/static-clang](https://github.com/dzbarsky/static-clang)
