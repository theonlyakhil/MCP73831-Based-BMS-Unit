# MCP73831-Based-BMS-Unit

## Introduction
-----------------------------------------------------

MCP73831 is linear charge management controller for Lithium-Ion and Lithium-Polymer batteries.
The device have a constant current , constant voltage charge algorithm that protects the battery while charging . In this project i have selected a 4.2V constant voltage device and the charging current can be varied by using the resistor connected to **PROG** pin of the **MCP73831**(R5), i have connected a 3.3K resistor to the **PROG** pin so that the charging current will be 330mA . 


                    Ireg = 1000V/Rprog  -> Equation for finding the Resistor Value 
                    Where:
                        Rprog in kOhms
                        Ireg in milliampere

The output from the Battery Management Module is connected to a 3.3v Linear Voltage Regulator(MCP1812BT). MCP1812BT is 300mA linear voltage regulator. 

## Push Button Circuit 
---------------------------------------------------------------

In the module i have provided a push button for controlling the output of the module . 

![push button schematic](https://github.com/theonlyakhil/MCP73831-Based-BMS-Unit/blob/main/Snap/pushbutton_ctrl.png)

Here **FDV304P** is a P-channel MOSFET that turns on when the push button is pressed and the source terminal of the MOSFET is connected to the anode of diode . The diode i have selected here is **BAV70L**, this is dual diode array in a single package (For providing reverse protection to other pin). Thus the REG_ENB line will become HIGH. This REG_ENB net is connected to the #SHDN pin of the output voltage regulator, whenever the #SHDN pin becomes HIGH the voltage regulator is switched ON , after turning ON the voltage regulator and then microcontroller (any of your choise ) the hold pin should be enabled immeatly , thus the output voltage regulator will remain in its ON state. For turning OFF the device the status of the push button can be read from the **POWER_BUTTON** by connecting it to an input pin of the microcontroller . After Detecting **POWER_BUTTON** state HIGH make the HOLD pin LOW through microcontroller , so both the input to the diode array will be come LOW , thus #SHDN pin of the regulator will become LOW and the regulator is turned OFF ..

## Some Snap Shots 
--------------------------------------------------------------------

### Schematic 

![Schematic](https://github.com/theonlyakhil/MCP73831-Based-BMS-Unit/blob/main/Snap/schematic.png)

### Top Layer 2D View

![top layer 2d](https://github.com/theonlyakhil/MCP73831-Based-BMS-Unit/blob/main/Snap/TopLayer_2d.png)

### Bottom Layer 2D View

![bottom layer 2d](https://github.com/theonlyakhil/MCP73831-Based-BMS-Unit/blob/main/Snap/BottomLayer_2d.png)

### Top View 3D

![Top view](https://github.com/theonlyakhil/MCP73831-Based-BMS-Unit/blob/main/Snap/TopView_3d.png)





