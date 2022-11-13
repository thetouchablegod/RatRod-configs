This is my printer config for Tevo Tornado running SRK mini v1.2. No webcam config currently.

I run Mainsail on a RasPi communicating via uart. That config is also here. 

START_PRINT and END_PRINT macros included. Comment out your start G-code in your slicer
and enter:

In start G-code
START_PRINT BED_TEMP={material_bed_temperature_layer_0} EXTRUDER_TEMP={material_print_temperature_layer_0}

In end G-code
END_PRINT