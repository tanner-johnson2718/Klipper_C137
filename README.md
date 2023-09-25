# Klipper C137

My home universe fork of Klipper. As of now the goal is to poke around and see whats up.

# Local Install and virtual MCU

## Build SimulAVR
```
sudo apt install g++ make cmake swig rst2pdf help2man texinfo
git clone git://git.savannah.nongnu.org/simulavr.git
cd simulavr
make python
make build  
```

## Configure and Build Klipper
```
cd /path/to/klipper
make menuconfig
```

* AVR atmega644p
* Extra low level options
* SIMULAVR software emulation support. Then one can compile
* `make`
* Run SimularAVR with: `PYTHONPATH=./simulavr/build/pysimulavr/ ./scripts/avrsim.py out/klipper.elf`
* Init klippy local env w/ `./scripts/install-debian.sh`
    * Creates dir @ ~/klippy-env
    * Adds python exes
    * Creates service @ /etc/systemd/system/klipper.service
        * Sym link @  /etc/systemd/system/multi-user.target.wants/klipper.service
    * Exe Actually Running: `/home/tanner/klippy-env/bin/python /home/tanner/Desktop/repos/Klipper_C137/klippy/klippy.py /home/tanner/printer.cfg -l /tmp/klippy.log`
* Kill the klippy process, we will invoke our own : `sudo systemctl stop klipper.service`
