# Overview
This repository contains Verilog code and Xilinx IP to display temperature values from a BMP180 on the 7-segment display of a Basys 3 FPGA. 

# Optimization
I did not have any resource limitations when coding this project, so it is not optimized for speed/resource utilization. A few things could be done to fix this: 

- Consolidate the duplicate adders and dividers. This can be done by modifying the divisor and dividend width and modifying the inputs to the divider as needed to handle sign conventions. 
- Clean up the intermediate variables. Some of the regs used in intermediate calculations (x1, x2, etc.) could be reused so that less resources are used.
- Optimize the timing of the state machine in calc_temp and i2c_master.

# Installation 
To program your Basys 3, follow these steps: 

- Clone this repository to your local machine.
- Open Vivado Tcl shell
- Using the shell, navigate to your repository using commands like "cd directory_name" and "cd .."
- Once your current directory is Basys_3_BMP_180 (check this by using "pwd"), copy and paste the code in the file "TCL_Script" to the console and click enter. 
- Once the Tcl script is done running, there should be a message in the console stating "Implementation done!"
- Open Vivado and program the Basys 3 as usual

# Notes 
I have tested this program with older versions of Vivado and the test bench. I am not 100% sure if it will work on the Basys 3, so please feel free to create issues if the program is not working for you. 
