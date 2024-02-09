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
1. navigate to the plutosdr-fw repo and dive into HDL folder and the project folder. Find the desire platform, in my case is Pluto
2. Run the makefile
```
    make
```
3. 