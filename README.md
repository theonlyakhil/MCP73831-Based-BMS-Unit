# MCP73831-Based-BMS-Unit

## Introduction
-----------------------------------------------------

MCP73831 is Linear Charge Management Controller for Lithium-Ion and Lithium-Polymer batteries.
The device has a constant current, constant voltage charge algorithm that protects the battery while charging. A 4.2V constant voltage device has been selected and the charging current can be varied by using the Resistor (R5) connected to **PROG** pin of the **MCP73831**. A 3.3K Resistor is connected to the **PROG** pin to  make the charging current 330mA. 
```
Equation for finding the Resistor Value
------------------------------------------
Ireg = 1000V/Rprog 
where:  Rprog in kOhms / Ireg in milliamperes
```
The output from the Battery Management Module is connected to a 3.3v 300mA Linear Voltage Regulator(MCP1812BT). 

## Push Button Circuit 
---------------------------------------------------------------

In the module, a push button is provided for controlling the output of the module. 

![push button schematic](https://github.com/theonlyakhil/MCP73831-Based-BMS-Unit/blob/main/Snap/pushbutton_ctrl.png)

Here **FDV304P** is a P-channel MOSFET that turns ON when the push button is pressed and the source terminal of the MOSFET is connected to the anode of diode. The diode  selected here is **BAV70L**, which is a dual diode array in a single package - for providing reverse protection with HOLD pin. Thus the REG_ENB line will become HIGH. This REG_ENB net is connected to the #SHDN pin of the output voltage regulator. Whenever the #SHDN pin becomes HIGH, the voltage regulator is switched ON. After turning ON the voltage regulator and then microcontroller of your choice, the HOLD pin should be enabled immediately. The output voltage regulator will now remain in its ON state. For turning OFF the device, the status of the push button can be read from the **POWER_BUTTON** by connecting it to an input pin of the microcontroller. After detecting **POWER_BUTTON** state as HIGH, make the HOLD pin LOW through microcontroller, so that both the input to the diode array will be come LOW. #SHDN pin of the regulator will then become LOW and the regulator is turned OFF.

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

![ISO VIEW](https://github.com/theonlyakhil/MCP73831-Based-BMS-Unit/blob/main/Snap/Iso_view.png)

All the design files are available at the Hardware Section in this Repository 

theonlyakhil :)


