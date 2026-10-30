# Linux Image Builder

A lightweight tool to build bootable SD card images for embedded Linux boards. Designed for fast kernel and driver development, without the complexity of **Yocto** or **Buildroot**.


## Toolchain

Install the cross compiling toolchain. 

```
sudo apt install gcc-arm-linux-gnueabi
```

## Compiling U-Boot

Clone the mainline U-boot sources:

```
git clone https://git.u-boot-project.org/u-boot/u-boot.git
git checkout v2018.05
export CROSS_COMPILE=arm-linux-gnueabi-
make am335x_boneblack_defconfig
```

To compile `u-boot.img` and `MLO`:
- Copy `u-boot-2018.05.config` file to `.config`
- Run `make`

To compile `u-boot.img.final` and `MLO.final`:
- Copy `u-boot-2018.05-final.config` file to `.config`
- Copy `uEnv.txt` file to `u-boot/`
- Run `make`
- This produces the `MLO` and `u-boot.img` files, rename them to `MLO.final` and `u-boot.img.final`
