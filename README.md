# zcu100
Xilinx config sources to enable OSL linux on zcu100 board

Tested opensource Linux on zcu100 board. 

Build steps:
	Please Refer below links for installing Xilinx tools and building linux images
https://xilinx-wiki.atlassian.net/wiki/spaces/A/pages/18842547/Install+Xilinx+Tools 
https://xilinx-wiki.atlassian.net/wiki/spaces/A/pages/18841722/ZCU102+Image+creation+in+OSL+flow 
	Steps for building linux and dtb images
o	git clone https://git.kernel.org/pub/scm/linux/kernel/git/torvalds/linux.git/  (master branch) 
o	make ARCH=arm64 xilinx_zynqmp_defconfig (copied the defconfig from repo)
o	make ARCH=arm64 CROSS_COMPILE=aarch64-linux-gnu- Image -j22
o	make ARCH=arm64 dtbs (zynqmp-zcu100-revC.dtb is the dtb we needed for testing this board)

	Copied the 2018.1 Petalinux pre-built boot.bin and image and zynqmp-zcu100-revC.dtb to the SD Card and booted linux.


