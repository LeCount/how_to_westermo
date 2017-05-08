Building NG
========================================================================
Remember not to use sudo all the time

General build steps
-------------------------------------------------------------------------
1. Clone down WeOS repoi
   `git clone git+ssh://USER@git.labs.westermo.se/home/git/Dragnet/weos.git`
2. Cd to WeOS folder
   `cd weos`
3. Pull / Update all submodules
   `git submodule update --init`
4. To build the first time, "Basis" is the main type for Lynx etc.
   `./bin/build.sh Basis/Standard`

Tips and tricks
-----------------------------------------------------------------------
* To build again without rebuilding everything
  `make`
* To build a specific part with extra build printouts
  `make V=1 cli-build`
* Use to see error-msgs that make sense
  `tail build.log`
* Add "export TFTPDIR=/srv/ftp" to ~/.bashrc to auto-copy img to /srv/ftp
* run 'dmesg' from the dut shell to printout the kernel log
* To rebuild kernel: 'touch kernel/linux-obj-Basis/.config'


General info
----------------------------------------------------------------------
Device trees is used to setup what kind of hardware we have. This is
done in 2 layers.

Examples:
Device tree all basis:     /products/family/Basis/Standard/dts/base.dtsi
Device tree lynx specific: /products/family/Basis/Standard/dts/cards/lynx-power.dtsi