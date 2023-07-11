# Comprehensive TCL Workshop: From Introduction to Advanced Scripting Techniques in Design and Synthesis
--------------------------------------------------------------------------------------------------------
_Author: Anush Kumar_

_Acknowledgements:_

_1.TCL Workshop by [Mr. Kunal Ghosh](https://github.com/kunalg123) , [VLSI System Design](https://www.vlsisystemdesign.com/)_

_2.T R Visruat_

_3.Geetima Kachari_

## Introduction
TCL (Tool Command Language) is a popular scripting language used for various purposes, such as rapid prototyping, automation, and extending applications. It has a straightforward syntax and is commonly used for tasks like file manipulation, text processing, and system administration. TCL allows users to write scripts that interact with other programs, execute commands, manipulate data, and perform various operations. It is known for its simplicity and flexibility, making it an accessible language for both beginners and experienced programmers.

1. [DAY-1](https://github.com/anushrx8/VSD_TCL_WORKSHOP/edit/main/README.md#day-1)
2. [DAY-2](https://github.com/anushrx8/VSD_TCL_WORKSHOP/edit/main/README.md#day-2)
3. [DAY-3](https://github.com/anushrx8/VSD_TCL_WORKSHOP/edit/main/README.md#day-3) 
4. [DAY-4](https://github.com/anushrx8/VSD_TCL_WORKSHOP/edit/main/README.md#day-4) 
5. [DAY-5](https://github.com/anushrx8/VSD_TCL_WORKSHOP/edit/main/README.md#day-5) 


## DAY-1

__Create Command (panda) and pass csv file from UNIC shell to Tcl script__

The command was created with the following algorithm:
1) letting the system know that its a UNIX script

```
#!/bin/tcsh -f  
```

2) Creating the logo

```
echo "        *******   **    **   *******      "
echo "        *******   ***   **   *******      "
echo "        **   **   ****  **   **   **      "
echo "        **   **   ** ** **   **   **      "
echo "        ******    **  ****   *******      "
echo "        **  ***   **   ***   **   **      "
echo "        **  ***   **    **   **   **      "
echo "        **  ***   **    **   **   **      "
echo
echo
echo "        TCL  COMMAND CREATED BY ANUSH     "

```

3) verifying three general scenarios for a user POV
  - user doesnt enter the csv file

![alt text](https://github.com/anushrx8/VSD_TCL_WORKSHOP/blob/main/assets/day1/2.png)


  - user enters the wrong csv file/ file doesnt exist


![alt text](https://github.com/anushrx8/VSD_TCL_WORKSHOP/blob/main/assets/day1/3.png)

  - user enters __-help__

![alt text](https://github.com/anushrx8/VSD_TCL_WORKSHOP/blob/main/assets/day1/4.png)



4) source the Unix shell to the Tcl script by passing the required csv file 

```
tclsh vsdsynth.tcl $argv[1] 
```
Note : Make sure the file is executable by using the command ``` chmod -R 777 panda ``` 

## DAY-2
__Converting inputs to format[1] and feeding it to yosys for synthesis__

  __- Create Variables__

![alt text](https://github.com/anushrx8/VSD_TCL_WORKSHOP/blob/main/assets/day2/1.png)

  __- Checking if the directories exist or not ( done to prevent the script from breaking )__

![alt text](https://github.com/anushrx8/VSD_TCL_WORKSHOP/blob/main/assets/day2/2.png)

Displays an error when the required file is not in the needed directory

![alt text](https://github.com/anushrx8/VSD_TCL_WORKSHOP/blob/main/assets/day2/3(2).png)


## DAY-3

__Read Constraints.csv file and convert to sdc format__

  - getting clock details from csv file and writing it the sdc file in the required format
  - getting input details from csv file and writing it in the required format
  - getting output details from csv file and writing it in the required format
 
Note: need to identify bussed and non bussed inputs and outputs before entering in the required format.

The script writing the sdc constraints.

![alt text](https://github.com/anushrx8/VSD_TCL_WORKSHOP/blob/main/assets/day3/1.png)

The sdc file 

![alt text](https://github.com/anushrx8/VSD_TCL_WORKSHOP/blob/main/assets/day3/2.png)

## DAY-4

### YOSYS (Yosys Open SYnthesis Suite)

YOSYS is an open-source RTL synthesis and formal verification framework for digital circuits. It takes RTL descriptions (e.g., Verilog) as input and performs synthesis to generate a gate-level netlist. YOSYS supports technology mapping, optimization, and formal verification. It has a scripting interface, integrates with other EDA tools, and is widely used in academia and industry for digital design tasks.

__Creating scripts for synthesis and running it on yosys__

  - creating script for Hierarchy check
  - running hierarchy check


__work in progress__

## DAY-5

__create script for OpenTimer and run STA analysis followed by generation of Quality of Results (QoR)__

_An introduction to procs_
  - To generate a script for OpenTimer, procs will be used. Procs are like functions in Python and are stored in an external tcl file. When sourced to the main tcl file, they perform a specified operation. One example of a proc is read_liberty, which takes options like -lib, -late, -early, and/or as arguments. By sourcing the proc in the main tcl script and mapping the arguments to the external tcl script, the read_liberty command is executed. The output of the proc is then available in the main tcl script.
  
__work in progress__
