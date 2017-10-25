# riscv-lld

This repository contains the RISC-V port of lld (the LLVM linker).

## Status

* Link static ELF executables
* Link dynamic ELF (PIE) executables and shared libraries
* Support for thread-local storage (TLS)
* Unit tests

Patches are submitted for review on LLVM phabricator.

**This repository will be regularly rebased onto lld master.**

## How to build

```
$ git clone https://github.com/llvm-mirror/llvm && cd llvm
$ git checkout f14ad9a908afbe3ed23911d23359d8380bcce29d
$ git clone https://github.com/andestech/lld tools/lld
$ mkdir build && cd build
$ cmake -DCMAKE_BUILD_TYPE=Release \
        -DLLVM_ENABLE_PROJECTS=lld \
        -DTARGETS_TO_BUILD= \
        -DEXPERIMENTAL_TARGETS_TO_BUILD=RISCV \
        ..
$ make lld
```

## Usage

You may invoke `ld.lld` directly or replace `ld` in the toolchain path with `ld.lld`:

```
$ cp bin/ld.lld ${path_to_toolchain}/bin/ld.lld
$ ln -sf ${path_to_toolchain}/bin/{ld.lld,ld}
```

## Issues

Please report issues related to the RISC-V port on GitHub's issue tracker.
