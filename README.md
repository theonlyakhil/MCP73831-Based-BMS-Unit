# MCP73831-Based-BMS-Unit

## Introduction
-----------------------------------------------------

MCP73831 is linear charge management controller for Lithium-Ion and Lithium-Polymer batteries.
The device have a constant current , constant voltage charge algorithm that protects the battery while charging . In this project i have selected a 4.2V constant voltage device and the charging current can be varied by using the resistor connected to **PROG** pin of the **MCP73831**(R5), i have connected a 3.3K resistor to the **PROG** pin so that the charging current will be 330mA . 


                    Ireg = 1000V/Rprog  -> Equation for finding the Resistor Value 
                    Where:
                        Rprog in kOhms
                        Ireg in milliampere



