# aarch-linux-gnu

These are my personal toolchains, cross compiled for aarch64. I currently use them for compiling [Flash Kernel](https://github.com/Flash-Kernel/angler).


## Supported operating systems

* Ubuntu based systems (built on 17.04)
* Arch based systems (built on standard Arch Linux, offshoots/forks may or may not work depending on how updated they are)


## Variants

* A standard GNU version, build straight from the [standard GCC source](https://gcc.gnu.org/git/?p=gcc.git) |
* A Linaro version, currently compiled from the [linaro-local/releases/linaro-6.3-2017.05](https://git.linaro.org/toolchain/gcc.git/log/?h=linaro-local/releases/linaro-6.3-2017.05) branch, merged with the [linaro-local/gcc-6-integration-branch](https://git.linaro.org/toolchain/gcc.git/log/?h=linaro-local/gcc-6-integration-branch).|


## Using these toolchains

To use these toolchains, do the following:

```bash
git clone https://github.com/nathanchance/aarch64-linux-gnu
cd aarch64-linux-gnu
tar -xvf --strip-components=1 <toolchain_name>.tar.xz
```

Then point your cross compiler to the toolchain. For kernels, you can do the following

```bash
export CROSS_COMPILE=$(pwd)/bin/aarch64-linux-gnu-
```

## Compiling these toolchains

You must first have all your dependencies installed. I recommend using [akhilnarang's setup scripts](https://github.com/akhilnarang/scripts). Otherwise, the Arch base-devel group or the following Ubuntu packages should suffice:

```bash
sudo apt-get install flex bison ncurses-dev texinfo gcc gperf patch libtool automake g++ libncurses5-dev gawk subversion expat libexpat1-dev python-all-dev binutils-static libgcc1:i386 bc libcloog-isl-dev libcap-dev autoconf libgmp-dev build-essential gcc-multilib g++-multilib pkg-config libmpc-dev libmpfr-dev
```

After installing your dependencies, run the following in a terminal to learn how to build:

```bash
git clone https://github.com/nathanchance/build-tools-gcc
cd build-tools-gcc
./build -h
```


## Questions?

If you have any questions or issues, please open an issue on this repo or the [build-tools-gcc](https://github.com/nathanchance/build-tools--gcc) repo and I'll do my best to assist you.
