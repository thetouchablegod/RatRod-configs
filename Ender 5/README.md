This is my printer config for Ender-5 running Octopus pro 1.1. The webcam is not currently configured.

I run Mainsail on a RasPi communicating via uart. That config is also here. 

START_PRINT and END_PRINT macros included. Comment out your start G-code in your slicer
and enter:

In start G-code:
```
START_PRINT BED_TEMP={material_bed_temperature_layer_0} EXTRUDER_TEMP={material_print_temperature_layer_0}
```

In end G-code:
```
END_PRINT

```
