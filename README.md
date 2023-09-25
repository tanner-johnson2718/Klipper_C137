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
