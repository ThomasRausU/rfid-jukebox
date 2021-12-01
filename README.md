# rfid-jukebox
yocto image example using meta-jukebox to build for a rpi zero 2 with wm8960 audio hat and MFRC522 RFID module

steps to build a image on a ubuntu 20.04

sudo apt install gawk wget git diffstat unzip texinfo gcc build-essential chrpath socat cpio python3 python3-pip python3-pexpect xz-utils debianutils iputils-ping python3-git python3-jinja2 libegl1-mesa libsdl1.2-dev pylint3 xterm python3-subunit mesa-common-dev zstd liblz4-tool
(more info here: https://docs.yoctoproject.org/3.4/brief-yoctoprojectqs/index.html)

git clone --recurse-submodules https://github.com/ThomasRausU/rfid-jukebox.git

source poky/oe-init-build-env 

bitbake jukebox-image
