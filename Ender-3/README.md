These are the configs for my Ender-3 running SKR Pico v 1.0.

I run Mainsail on a RasPi communicating via uart. That config is also here. 

START_PRINT and END_PRINT macros are in the wrong place. They should be put into mainsail.cfg and will be moved.

Comment out your start G-code in your slicer
and enter:

In start G-code
START_PRINT BED_TEMP={material_bed_temperature_layer_0} EXTRUDER_TEMP={material_print_temperature_layer_0}

In end G-code
END_PRINT