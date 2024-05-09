These are the configs for my Ender-3 running SKR Pico v 1.0.

I run Mainsail on a RasPi communicating via uart. That config is also here. 

START_PRINT and END_PRINT macros are in the wrong place. They should be put into mainsail.cfg and will be moved.

Comment out your start G-code in your slicer
and enter something like:

    For Orca Slicer:
    START_PRINT BED_TEMP=[bed_temperature_initial_layer_single] EXTRUDER_TEMP=[nozzle_temperature_initial_layer]

    In end G-code
    END_PRINT
