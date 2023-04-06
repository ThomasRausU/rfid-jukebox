# yocto-rfid-jukebox
yocto image example using [meta-jukebox](https://github.com/ThomasRausU/meta-jukebox), a yocto layer for [phoniebox v3](http://phoniebox.de/) to build for a rpi zero 2 with wm8960 audio hat and MFRC522 RFID module

# steps to build a image on a ubuntu 20.04

## install required build tools on the build host

    sudo apt install gawk wget git diffstat unzip texinfo gcc build-essential chrpath socat cpio python3 python3-pip python3-pexpect xz-utils debianutils iputils-ping python3-git python3-jinja2 libegl1-mesa libsdl1.2-dev pylint3 xterm python3-subunit mesa-common-dev zstd liblz4-tool

(more info here: https://docs.yoctoproject.org/3.4/brief-yoctoprojectqs/index.html)

## clone the source code

    git clone --recurse-submodules https://github.com/ThomasRausU/yocto-rfid-jukebox.git

## build the image
    cd yocto-rfid-jukebox/poky && TEMPLATECONF=../conf/templates/ . oe-init-build-env ../build

    bitbake jukebox-image

## write image to sd card
    sudo dd if=build/tmp/deploy/images/raspberrypi0-2w-64/jukebox-image-raspberrypi0-2w-64.wic of=/dev/sdXXX
