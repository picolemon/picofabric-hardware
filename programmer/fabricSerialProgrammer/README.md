# PicoFabric Serial Programmer # 
[![Install](https://img.shields.io/badge/VSCode-Extension-f3cd5a?longCache=true&style=flat-rounded)](https://github.com/picolemon/picofabric-ide)
[![datasheet (pdf)](https://img.shields.io/badge/Data%20Sheet-PDF-f3cd5a?longCache=true&style=flat-rounded)](https://github.com/picolemon/picofabric-hardware/blob/main/doc/datasheet.pdf)
[![sch (pdf)](https://img.shields.io/badge/SCH-PDF-f3cd5a?longCache=true&style=flat-rounded)](https://github.com/picolemon/picofabric-hardware/blob/main/doc/sch.pdf)
[![Store](https://img.shields.io/badge/Store-PicoLemon-f3cd5a?longCache=true&style=flat-rounded)](http://picolemon.com/board/PICOFABRIC)
[![Examples](https://img.shields.io/badge/Code-Examples-f3cd5a?longCache=true&style=flat-rounded)](https://github.com/picolemon/picofabric-examples)
[![Discord](https://img.shields.io/badge/@-Discord-f3cd5a?longCache=true&style=flat-rounded)](https://discord.gg/Be3yFCzyrp)

## Overview
Programs the PicoFabric board over USB using a UF2 bootloader on the Pico.


## Whats included
- [x] Python based program.py programmer 
- [x] Blinky test
- [x] UF2 bootloader

## Installation

- Download and install [Python](https://www.python.org/) (3.0 or above), make sure pip or pip3 package manager is installed as some python packages are required.
- Install the pyserial python package required for the built in FPGA programmer for programming on the CLI, the extension includes a built in programmer which python is not required.
```
$ pip3 install pyserial
```
- Copy the [fabric_bootloader.uf2](uf2/pico/) image to the Pico using BOOTSEL mode.


## Testing

Plug-in the PicoFabric device into a USB port and run the following command. Extract the repo or git clone and cd into the programmer directory.
```
$ cd programmer/fabricSerialProgrammer
$ python3 program.py --test

[debug] Creating serial link for port /dev/ttyACM0
[info] Found 1 device
[info] [Auto select] Using device 'usbserial:///dev/ttyACM0'
[info] Testing device at 'usbserial:///dev/ttyACM0'
[info] status: ok
[info] fpgaDeviceId: 554766403
[info] uid: e660913c34b8321
[info] deviceOk: 1
```

## Programming

Build a valid bitstream using Lattice Diamond, PicoFabric IDE or a ECP5 based tool. A sample bitstream is provided in the bitstreams/ folder.
```
$ cd programmer/fabricSerialProgrammer
$ python3 program.py bitstreams/blinky.bit

[info] Uploading bitstream 'bitstreams/blinky.bit' to 'usbserial:///dev/ttyACM0', is saving: None
[progress] Chunk 0 / 582369
[progress] Chunk 4064 / 582369
...
[progress] Chunk 581152 / 582369
[progress] Completed 582369 / 582369
[info] Bitstream programmed on device 'usbserial:///dev/ttyACM0'

```

## Related Libraries
- [x] [PicoFabric MicroPython library](https://github.com/picolemon/picofabric-micropython)
- [x] [PicoFabric C/C++ library](https://github.com/picolemon/picofabric-c)
- [x] [VHDL, C & Python examples](https://github.com/picolemon/picofabric-examples)
- [x] [Pico Fabric IDE](https://github.com/picolemon/picofabric-ide)


## Support
- Drop by the [discord](https://discord.gg/Be3yFCzyrp)
- Email help@picolemon.com

Copyright (c) 2023 picoLemon
