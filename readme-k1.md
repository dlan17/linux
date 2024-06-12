
====== Policy ======

* Warning:
   this branch will be constantly rebased to the most recent tag of linus' tree,
   mostly will use 'git push --force', so backup old git tree if you needed.

* No grantee all drivers will work.

====== Version ======

* based on : 6.10-rc3

====== Drivers ======

* dts basic:
* uart/serial:
* irqchip
* regulator
* reset
* clock
* pinctrl
* gpio
* i2c -> mfd
* pm domain
* soc (pm domain / reboot control / dma range)
* dmaengine
* mmc/sdhc
* ethernet
* pcie: nvme
* usb: input: mouse/keyboard
* usb: mass storage device
* wathdog
* thermal

====== Compiling ======

* alias rvmake='make ARCH=riscv CROSS_COMPILE=riscv64-unknown-linux-gnu- '
* rvmake k1_defconfig && rvmake Image && rvmake modules

====== Bootargs ======

 earlycon=pxa_serial,0xd4017000  earlyprintk console=ttyS0,115200 loglevel=8 root=/dev/mmcblk2p3 rootwait rootfstype=ext4 regulator_ignore_unused clk_ignore_unused

====== Known issue ======

* vendor driver has not not been ported to this branch
  - wifi, wireless/realtek
  - media, drivers/media
  - gpu
  - sound
  - crypto
