Most of the interesting files are in the `magic_files/` folder
Here are the commands to run for each of these steps:


##### LVS
From magic:
    extract all
    ext2spice lvs
    ext2spice -o osc_adj_lvs.spice

From the `magic_files/` folder:
    module load netgen
    export PDKPATH="/afs/ir.stanford.edu/class/ee272/PDKS/sky130A"
    netgen -batch lvs "../netlist_from_xschem.spice osc_adj" "osc_adj_lvs.spice test_osc_adj" $PDKPATH/libs.tech/netgen/sky130A_setup.tcl


##### PEX
From magic:
    extract all
    ext2spice lvs
    ext2spice cthresh 0
    ext2spice rthresh 0
    ext2spice -o osc_adj_pex.spice

##### GDS
From magic:
    gds write osc_adj.gdsV


##### LEF
From magic:
    lef write osc_adj.lef

