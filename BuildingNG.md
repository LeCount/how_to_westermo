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
