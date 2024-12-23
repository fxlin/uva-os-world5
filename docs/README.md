# UVA-OS Lab5 "Rice User" 
## To UVA students: the code will become available in Sp25

This is the last part of the UVA-OS class (CS4414/CS6456). 

[OVERVIEW](https://github.com/fxlin/cs4414-main) |
[PROTO1](https://github.com/fxlin/uva-os-world1) |
[PROTO2](https://github.com/fxlin/uva-os-world2) |
[PROTO3](https://github.com/fxlin/uva-os-world3) |
[PROTO4](https://github.com/fxlin/uva-os-world4) |
[PROTO5](https://github.com/fxlin/uva-os-world5) 

Students: see [quests-lab5.md](quests-lab5.md)

## GALLERY

https://github.com/user-attachments/assets/3d7bdf38-25d8-46dc-9f1a-8e0624e0c78f


https://github.com/user-attachments/assets/991ec275-7620-42ec-bb9c-39762b5ad080


## DESIGNS

The OS now includes a full libc (`newlib`) and miniature libSDL (for input/output functions), 
atop which we port additional applications, including a shell, a music player, a blockchain miner, and DOOM (1993). 
To enable easy file exchanges between our OS and PC/Mac machines, we also 
bring up the SD card driver and port FAT32 filesystem support.
We implement a desktop environment, comprising a simple window manager and a input dispatcher, 
so that multiple apps be rendered on the screen concurrently.
Eventually, we bring up all four CPU cores to unleash full power of the Raspberry Pi 3.

![alt text](Slide9.PNG)

This OS introduces virtual memory and user/kernel separation. It provides syscalls and can run one or multiple "Mario" applications concurrently in userspace.

✅ libc (newlib)

✅ SDL 

✅ SD card

✅ FAT32

✅ DOOM

✅ Desktop

✅ Multicore

✅ Waveshare Raspberry Pi GAMEHAT

## Build

```sh
# for QEMU
export PLAT=rpi3qemu
# or, for rpi3
export PLAT=rpi3
```

To clean up:
```sh
./cleanall.sh
./cleanuser.sh  # clean user programs only
```

To build everything:
```sh
./makeall.sh
```

## Run

To run on QEMU:
```sh
./run-rpi3qemu.sh
```

To run on rpi3:
(WSL2) To copy the kernel image to `d:/tmp/`:
```sh
cp kernel8-rpi3.img /mnt/d/tmp/kernel8-rpi3.img
```

Insert SD card, copy to SD card:
```sh
copy "d:\tmp\kernel8-rpi3.img" f:\kernel8-rpi3.img
```

Faster way:
Copy `scripts/9999-download.bat` and `scripts/delay-exit.bat` to Windows desktop, then double-click `9999-download.bat`.
