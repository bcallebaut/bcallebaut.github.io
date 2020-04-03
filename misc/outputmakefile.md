Bulding source code out of the source tree is a good practive in order to avoid cluttering your source tree.
It makes also the cleaning of the source tree much easier as you only have to remove the build tree. It allows you also to keep multiple build trees with different configurations

I use it a lot with [cmake](https://cmake.org) based makefiles but never until now with the [Linux Kernel](https://kernel.org)

# Procedure

The makefile of the linux kernel defines a target specifically for that called *outputmakefile*.

The procedure is a follow:
1. create your build directory outside of the source tree (eg : mkdir ../build)
2. execute : *make outputmakefile*
3. execute : *make defconfig* or *make menuconfig* (you must have libcurse-dev installed in this case)
4. Build your kernel *make ; make moodules*