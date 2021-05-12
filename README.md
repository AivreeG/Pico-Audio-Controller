# Pico Audio Controller

Source code to compile an image for the Raspberry Pi Pico to be used as a USB audio controller/mixer.

_**There is currently no functionality whatsoever. The USB device attaches and provides proper USB Descriptor information but that is all.**_

## Setup
**This is to build the project from source. If you want the precompiled `uf2` file, you'll find it in the `build` directory.**

Clone the Raspberry Pi Pico SDK, and update the submodules. You can optionally create a new directory somewhere in your `$HOME` directory to keep it. 

```bash
cd dir-to-keep-sdk
git clone -b master https://github.com/raspberrypi/pico-sdk.git
cd pico-sdk
git submodule update --init
```

You can either set the `PICO_SDK_PATH` environment variable each time before you build, or update your shell's `.rc` file (.bashrc, .zshrc, etc).

```bash
...
export PICO_SDK_PATH=/absolute/path/to/dir-to-keep-sdk/pico-sdk
...
```

The [Pico SDK Documentation](https://github.com/raspberrypi/pico-sdk) states you need [Cmake](https://cmake.org) and the [GNU Embedded Toolchain for Arm](https://developer.arm.com/tools-and-software/open-source-software/developer-tools/gnu-toolchain/gnu-rm/downloads). In Debian and its derivatives, you would do so as follows.

```bash
sudo apt update
sudo apt install cmake gcc-arm-none-eabi libnewlib-arm-none-eabi
```

Other distros have slightly different names for the packages. For example in Arch/Manjaro:

```bash
sudo pacman -Sy cmake arm-none-eabi-gcc arm-none-eabi-newlib
```

You should also have `gcc` and `g++` installed.

You can find more information on installing the SDK as well as some automated ways to do so in the [Raspberry Pi Pico C/C++ Getting Started](https://rptl.io/pico-get-started) document. 

## Building

When you want to build the project, enter the `build` directory, and run `cmake` on the `src` directory. Then run `make`.

```bash
cd build
cmake ../src
make
```

Lots of files will be produced from this. Of these is the `uf2` file to flash onto the Pico. Building should be that simple.

## Usage

N/A