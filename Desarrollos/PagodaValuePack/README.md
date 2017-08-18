## Pagoda FPV 5.8GHz antenna
Pagoda V2 Antenna by Maarten Baert panelized in a value pack including 3 copies of Pagoda PCB's with breakaway alignment struts, a modified assembly jig, a ruler for measuring the coax length, a coax stripping depth gauge for RP-SMA center contacts and a template for cutting
styrofoam discs to fill the pagoda, all of that on a single 10x10cm board. 

THIS IS EXPERIMENTAL, DO NOT USE THESE FILES FOR ORDERING UNTIL FURTHER NOTICE.
An experimental batch has been sent to elecrow to see if it can be manufactured at all and if the assembly jig works. Cost per PCB is $1.70 at elecrow using their 10x green PCB 10x10cm special offer. That's $0.57 per pagoda PCB pack.

EDIT:
Boards arrived, the concept DOES work, PCB milling is spot on and, as the assembly jig is heat ressistant and self aligned, pagodas can be mass-soldered in an oven with them. However, its VERY hard to separate the boards as intended in the design without prematurely breaking the aligmnent-support tabs. A new version to solve this issue is on its way. DO NOT ORDER ANYTHING FROM THE CURRENT FILES!

EDIT:
Added new PagodaAltiumPack which contains:
-All Pagoda design files (LHCP and RHCP, versions V2 and V2B) in editable Altium Designer PCB format. PCB's are recreated from maarten's script using arcs and lines. Text silkscreen has been adjusted but it's not a perfect fit for the original. Everything else should be OK. An statistically significant sample of the files' gerber exports has been checked against official gerbers and they match perfectly (apart from silkscreen and a slight (below milling tolerance) rounding I made to the PCB diameters.
-All PagodaValuePackV2 design files (LHCP and RHCP, versions V2 and V2B) to order at DirtyPCBs or similar manufacturers which don't charge extra for panels. These files are UNTESTED for now, but issues with old valuepack should be at least partially fixed.

We have tried to convert the design files to Kicad and/or Eagle and/or any PCB exchange format such as PCAD but results aren't great as 
some pagoda features require software-dependant geometrical constructions.

EDIT:
PagodaAltiumPack files got ordered and tested. Results are good, once you get used to separating the PCB's. Separation can't be done realiably by hand, some sort of small cutting pliers are required. Jigs work well, as intended. A new version may be released with minor tolerance adjustments to make assembly even easier, but files are in ORDERABLE state.


For project details go here:
[http://www.maartenbaert.be/quadcopters/antennas/pagoda-antenna/]
