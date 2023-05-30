This is my printer config for Tevo Tornado running SRK mini e3 v 3.0. Crowsnest configured

I run Mainsail on an old laptop running Debian 11. That config is also here. 

START_PRINT and END_PRINT macros included. Comment out your start G-code in your slicer
and enter something like:

In start G-code
START_PRINT BED_TEMP={material_bed_temperature_layer_0} EXTRUDER_TEMP={material_print_temperature_layer_0}

In end G-code
END_PRINT

You may have to look up variable names for your particular slicer.

