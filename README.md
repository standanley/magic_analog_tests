## Example files for analog layout in Magic
Most of the interesting files are in the `magic_files/` folder.
Below are the commands to run for various magic functions.


#### LVS
From magic:

    extract all
    ext2spice lvs
    ext2spice -o osc_adj_lvs.spice

From the `magic_files/` folder:

    module load netgen
    export PDKPATH="/afs/ir.stanford.edu/class/ee272/PDKS/sky130A"
    netgen -batch lvs "../netlist_from_xschem.spice osc_adj" "osc_adj_lvs.spice test_osc_adj" $PDKPATH/libs.tech/netgen/sky130A_setup.tcl


#### PEX
From magic:

    extract all
    ext2spice lvs
    ext2spice cthresh 0
    ext2spice rthresh 0
    ext2spice -o osc_adj_pex.spice

#### GDS
From magic:

    gds write osc_adj.gds

#### LEF
From magic:

    lef write osc_adj.lef

### Some useful magic shortcuts
|     Macro                       |     Result                                                                                                  |
|---------------------------------|-------------------------------------------------------------------------------------------------------------|
|     s                           |     Select the thing under the cursor.   Pressing it multiple times cycles through different selections.    |
|     Left click / Right click    |     Move the lower-left of the box to the   cursor / set the upper-right of the box to the cursor           |
|     Middle click                |     Paint the box with whatever layers the   cursor is over                                                 |
|     z / Z                       |     zoom in / Zoom out                                                                                      |
|     m / c                       |     Move / copy the selection to the cursor                                                                 |
|     :label                      |     Create a label where the box is                                                                         |
|     :findlabel abc              |     Select the label with name “abc”                                                                        |
|     :port make                  |     Turn the selected label into a port.   The “port” command can also set the direction/use of a port.     |
|     u / U                       |     undo / redo                                                                                             |

More info about these commands and more at http://opencircuitdesign.com/magic/userguide.html
