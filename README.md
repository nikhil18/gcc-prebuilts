# Prebuilt GCC toolchains

These are my personal toolchains, cross compiled for arm and aarch64. I currently use them for compiling [Flash Kernel](https://github.com/nathanchance/angler). They are compiled with [crosstool-NG](http://crosstool-ng.github.io), configs are included as well.


## Supported operating systems

Most if not all versions of Linux should work with these as they are statically linked. Let me know if there are any issues following the questions section below.


## Variants

* A standard GNU version, build straight from the [standard GCC source](https://gcc.gnu.org/git/?p=gcc.git)
* A Linaro version, currently compiled from the [linaro-local/releases/linaro-6.3-2017.05](https://git.linaro.org/toolchain/gcc.git/log/?h=linaro-local/releases/linaro-6.3-2017.05) branch


## Using these toolchains

To use these toolchains, do the following:

```bash
git clone https://github.com/nathanchance/gcc-prebuilts
cd aarch64-linux-gnu
tar -xvf <toolchain_name>.tar.xz --strip-components=1
```

Then point your cross compiler to the toolchain. For kernels, you can do the following

```bash
# for arm64
export CROSS_COMPILE=$(pwd)/bin/aarch64-linaro-linux-gnueabi-

# for arm
export CROSS_COMPILE=$(pwd)/bin/arm-linaro-linux-gnueabi-
```

## Compiling these toolchains

If you would like to learn how to compile these toolchains, please give [this README](https://github.com/nathanchance/build-tools-gcc/blob/master/README.md) a glance.


## Questions?

If you have any questions or issues, please open an issue on this repo or the [build-tools-gcc](https://github.com/nathanchance/build-tools-gcc) repo OR make a post in [the XDA thread](https://forum.xda-developers.com/android/development/toolchains-gnu-linaro-5th-2017-t3606941) and I'll do my best to assist you.
