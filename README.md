## Introduction
The basic goal of this repository is documenting and providing everything necessary for building a modern smartphone from scratch under a free software license. I'm under no illusions that this can be done in a short time, my timeline for having a working prototype is ~10 years. 

One of the main priorities of creating this document is attracting like-minded people who care about consumer freedoms and have the necessary expertise(electrical/electronic engineers, hardware designers, software designers, and so on..) to the cause. If you are willing to help, please do not hesitate to contact me by creating an issue on the GitHub repo, or any other channels I'm available under the same username.

## Goals
* Use over the shelf electronics to build a modern smartphone
* Use free software/hardware where ever we can, while doing it

## Nongoals
* Optimizing for profit or other current tech market priorities

## Design goals

### SOC
This is already somewhat possible with the emerging ecosystem of RISC-v based CPUs/SOCs. We will have to evaluate the existing projects and change them to fit our needs. The SOC will have to include a GPU and other peripherals(video decoders, camera drivers, etc..) required to build a modern smartphone.

### Baseband
This is probably going to be the hardest goal since none of the available baseband chipsets are "open" in the least sense of the word right now. And even if we build one, we'll have to deal with the compliance issues(we'll cross that bridge if we ever come to it). Nonetheless, building free baseband hardware and firmware is one of the major goals of the project. To keep the project less complex, we are probably better off targeting only LTE or 5G for now.

### Software
This is the part we have to worry about the least(except baseband/wifi firmware) since there are a lot of free mobile operating systems out there. We should probably get Linux running and then we can target android, ubports, etc..

### Overall
Since fabricating a custom chip is going to cost a lot, at least initially we'll have to target for an FPGA based device. I don't know that much about how this will work out in terms of cost and CPU frequency/capacity etc.. We'll need some experts to chime in here, we can explore lattice FPGAs as a first choice since at least some of them are supported by free toolchains like symbiflow. Ideally, we should design and put all of our custom digital hardware(CPU/GPU/Baseband) on one gigantic FPGA. We can also use off the shelf DRAM chips, FLASH chips and probably displays/cameras without compromising our "free" ideals. 

## Links
### CPU/SOC/GPU
* [risc-v](https://riscv.org/)
* risc-v SOC: [rocket chip](https://github.com/chipsalliance/rocket-chip)
* risc-v SOC: [shakti](https://shakti.org.in/)
* risc-v CPU: [VexRiscv](https://github.com/SpinalHDL/VexRiscv) -- optimized for fpga, looks like a better fit.
* risc-v GPU: [libresoc](https://libre-riscv.org/3d_gpu/)

### Baseband/wifi/bluetooth
* celullar : [maybe osmocom?](https://osmocom.org/)
* wifi: [openwifi](https://github.com/open-sdr/openwifi)
* bluetooth [opercores](https://opencores.org/projects/bluetooth)

### tools
* [symbiflow](https://symbiflow.github.io/)
