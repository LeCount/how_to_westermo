Uppgrade to Barabox on Basis/lynx:
1. download 2014 version of barebox from jenkins
2. copy it to some place on the dut. (with scp for example)
3. Check where the boot is loocated on the dut
4. flash_unlock <that path>
5. flash_eraseall <that path>
6. flashcp <basispath> <bootpath>

Barebox Tips'n tricks:
To change boot order
1. Restart dut while holding ctrl+c
2. edit /env/etc/order
3. Add "net" to top
4. saveenv /dev/etc /env/etc
5. reset
