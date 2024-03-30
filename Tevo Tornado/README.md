This is my printer config for Tevo Tornado running SRK mini e3 v 3.0. Crowsnest configured

I run Mainsail on an old laptop running Debian 11. That config is also here. 

START_PRINT and END_PRINT macros included. Comment out your start G-code in your slicer
and enter:

For Cura
In start G-code:
```
  START_PRINT BED_TEMP={material_bed_temperature_layer_0} EXTRUDER_TEMP={material_print_temperature_layer_0}
```

In end G-code:
```
  END_PRINT
```

Superslicer based 
Start gcode:
```
M140 S0
M104 S0
G92 E0
START_PRINT EXTRUDER_TEMP=[first_layer_temperature] BED_TEMP=[first_layer_bed_temperature]
```
End gcode:
  ```
   END_PRINT
```
You may have to look up variable names for your particular slicer.

Macro to be put into into mainsail.cfg or a sererate file thats included in Klipper.cfg.
```
  [gcode_macro START_PRINT]
gcode:
    {% set BED_TEMP = params.BED_TEMP|default(80)|float %}
    {% set EXTRUDER_TEMP = params.EXTRUDER_TEMP|default(210)|float %}
    # load default bed mesh
    BED_MESH_PROFILE LOAD=default
    # Start bed heating
    M140 S{BED_TEMP}
    # Use absolute coordinates
    G90
    # Reset the G-Code Z offset (adjust Z offset if needed)
    SET_GCODE_OFFSET Z=0.0
    # Home the printer
    G28
    # Move the nozzle near the bed
    G1 Z5 F3000
    # Move the nozzle very close to the bed
    G1 Z0.15 F300
    # Wait for bed to reach temperature
    M190 S{BED_TEMP}
    # Set and wait for nozzle to reach temperature
    M109 S{EXTRUDER_TEMP}

[gcode_macro END_PRINT]
gcode:
    # Turn off bed, extruder, and fan
    M140 S0
    M104 S0
    M106 S0
    # Move nozzle away from print while retracting
    G91
    G1 X-2 Y-2 E-3 F300
    # Raise nozzle by 10mm
    G1 Z10 F3000
    G90
    # Disable steppers
    # M84
```
