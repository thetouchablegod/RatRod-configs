This is a place to store my Klipper configs for my machines.

    -Ender 3
    -Ender 5 Pro
    -Tevo Tornado

The configs may be useful to you as a statring point for your machines. You must be aware
that my machines are modified. These modifications affect configuration in some
ways. I will do my best to note them all here now. Proper commenting within configs 
is on the TODO list.

Ender 3

    -Mainboard: Big Tree Tech (BTT) SKR Pico connected to RPi via UART
    -Linear rail on Y axis - I lose ~20mm because of this
    -The belt tensioner I use loses me between 3-5mm on the X axis. 
        -I have ignored this safely by knowing my limits in the slicer, 
         but I may change it in the future.

Ender 5

    -Mainboard: Big Tree Tech Octopus Pro 1.1 connected to RPi via UART
        -TCM2209 Drivers
        -The default Ender-5 screen works now. 
    
Tevo Tornado
    -Creality Cr-10 clone
    -Mainboard: SKR mini e3 v3.0 connected to Laptop via USB
    -Same belt tensioner on the X axis as my Ender-3, but have not found any loss of motion
