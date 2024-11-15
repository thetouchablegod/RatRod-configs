These are the configs for my Ender-3 running SKR 1.4 Turbo
I run Mainsail on an Orangepi Zero 3 communicating via USB.

To use built-in macros, Comment out your start G-code in your slicer
and enter something like:

    For Orca Slicer start gcode:
    START_PRINT BED_TEMP=[bed_temperature_initial_layer_single] EXTRUDER_TEMP=[nozzle_temperature_initial_layer]

    In end G-code:
    END_PRINT
    