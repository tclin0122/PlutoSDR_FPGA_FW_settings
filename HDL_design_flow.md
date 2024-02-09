# HDL design

## Intro
This md file records how to use Vivado to update the FPGA of PlutoSDR

## Folder structure in Pluto project inside hdl project
```
    .
    ├── Makefile               # Automatic script to build the vivado project
    ├── system_bd.tcl          # Script to create board design
    ├── system_constr.xdc      # Constraints for PlutoSDR
    ├── system_project.tcl     # Path and initial setup scripts
    ├── system_top.v           # Top design
    └── README.md
```

## Steps
1. navigate to the plutosdr-fw repo and dive into HDL folder and the project folder. Find the desire platform, in my case is Pluto [1]
![Architecture](/image/Screenshot%202024-02-09%20at%2005-33-21%20pluto%20-%20Analog%20Devices%20Inc.%20Transceiver%20Toolbox.png)
2. Design your customized IP (Matlab HDL compiler or Directly design the HDL)
3. Connect all the design IO in system_bd.tcl
4. Run the makefile
```
    $ make
```
 


## Reference
[1] pluto Reference Design Integration: [URL link](https://analogdevicesinc.github.io/TransceiverToolbox/mkdocs/hdlrefdesigns/pluto/)