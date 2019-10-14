# toolchain
gcc-linaro-7.4.1-2019.02-x86_64_aarch64-linux-gnu.tar.xz	Download official website(https://www.linaro.org/downloads)

# arm-trusted-firmware-master
init code：
	git clone https://github.com/ARM-software/arm-trusted-firmware.git

build：
	make CROSS_COMPILE=aarch64-linux-gnu- PLAT=sun50i_a64 DEBUG=1 bl31

# uboot
init code：
	https://ftp.denx.de/pub/u-boot/u-boot-2019.07.tar.bz2

build(aboot BL31 please read the section on ARM Trusted Firmware (ATF) in board/sunxi/README.sunxi64)：
	make CROSS_COMPILE=aarch64-linux-gnu- BL31=~/work/linux/1.uboot/uboot/arm-trusted-firmware-master/build/sun50i_a64/debug/bl31.bin

Install Bootloader to the SD-Card(For more information, please refer to http://linux-sunxi.org/Bootable_SD_card#Bootloader);
	sudo dd if=u-boot-sunxi-with-spl.bin of=/dev/sdb bs=1k seek=8