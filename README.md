# PlutoSDR_FPGA_FW_settings

## Introduction
This is a repo for me to record how to update the firmware and adjust the IP for PlutoSDR

## Tools and software lists
### Hardware
    - Lenovo P1 gen 2 with Linux Ubuntu 22.04.03
    - ADALM-PLUTO Rev.C 
### Software
    - Vivado: Version 2021.1
    - Matlab: Version 2021a
    - Buildroot
    - Linaro Binary Toolchain: Version 7.3-2018.05 7.3.1

## Preparation
1. Install the GCC tools that is compatible to Buildroot. \href{}{} **Linaro GCC Version: 7.3-2018.05 7.3.1** will be used, which can download via [Link](https://releases.linaro.org/components/toolchain/binaries/7.3-2018.05/arm-linux-gnueabihf/) here.
2. Download ***gcc-linaro-7.3.1-2018.05-x86_64_arm-linux-gnueabihf.tar.xz*** and put it into this directory: **/opt/**
3. uncompress the gcc file with:
```
    tar -xvJf gcc-linaro-7.3.1-2018.05-x86_64_arm-linux-gnueabihf.tar.xz
```
4. Jump to the root and set the environment
```
    cd 
    vim ~/.bashrc
```
5. add the Path and then source the bashrc file
```
    export PATH=/opt/gcc-linaro-7.3.1-2018.05-x86_64_arm-linux-gnueabihf/bin:$PATH
```

6. Build the needed tools for fw update
```
    sudo apt-get install git build-essential fakeroot libncurses5-dev libssl-dev ccache
    sudo apt-get install dfu-util u-boot-tools device-tree-compiler mtools
    sudo apt install -y git build-essential wget cpio unzip rsync bc libncurses5-dev screen
    sudo apt-get install libmpc-dev
    wget http://archive.ubuntu.com/ubuntu/pool/main/o/openssl/libssl1.1_1.1.0g-2ubuntu4_amd64.deb
    sudo dpkg -i libssl1.1_1.1.0g-2ubuntu4_amd64.deb
```
7. Clone the plutosdr-fw repo and set the environment to the Vivado version
```
    git clone --recursive https://github.com/analogdevicesinc/plutosdr-fw.git
    cd plutosdr-fw
    export VIVADO_SETTINGS=/opt/Xilinx/Vivado/2021.2/settings64.sh
```
8. Design and integrate the HDL (Optional) 
9. Build the project
```
    make
``` 