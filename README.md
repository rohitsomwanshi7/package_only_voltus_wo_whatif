# package_only_voltus_wo_whatif
This script creates a dummy voltage source on first def shape - to avoid no resistance in grid error at MG.
Flow utilizes dynamic era (early rail) analysis where user does not need to give PGVs.

Run package only simulation in Voltus
Included run.pl perl script to create test.tcl Voltus run script.
Use model: perl run.pl <config.txt>
config.txt file format:
net <net_name> <type = POWER/GROUND> <ploc location> <nominal voltage>
tlef <tech lef file location>
exttech <extraction tech (qrcTechFile) location>
pkg <subcircuit name> <package model path> <package mapping file>
pwl <layer> <pwl data>

Example:
net VDD_PCPU POWER plocs/accp.VDD_PCPU.ploc 0.9
tlef example.tlef
exttech qrcTechFile
pkg example_top sample_pkg.ckt pkg_mapping_file
pwl M12 0ns 0mA 1ns 0mA 1.9ns 0mA 2ns 10mA 4ns 0mA
