# Workflow for Creating and Working on an STM32 Project

With VSCode, CubeMX, OpenOCD, STM32-for-VSCode
Reasoning: STM32CubeIde is pretty good, but there are a handful of troubling errors that can't be easily mitigated without fully migrating to another more modular solution.

## Generate Project
* Generate project with CubeMX
* Set the Toolchain / IDE to `Makefile`

Select these boxes:
* Project Manager > Code Generator > "Generate peripheral initialization as pair of .c/.h files
* Copy all used libraries into the project folder
* Auto backup all files on regeneration

### Using CubeMX and Avoiding Auto Generated Code
* Create an actual main function called `<program_name>.c` and call it before the while loop in `main.c`
* This won't be touched by the auto code generated which means cleaner code and code won't be messed with

## Working on the Code
* Use Visual Studio Code
* Extensions to Install: STM32 for VSCode

### Formatting
* The output of CubeMX is formatted using 2 space indents instead of the commonly used 4 space indents
* Instead of reformatting the code every time that it is regenerated, in VSCode, merge the files in `.vscode` into the current directory to switch all C and CPP files to 2 spaces.


## Modify STM32 Peripherals
* 


## Version Control
* Use the `.gitignore` file in this directory and `git init`


# Debugging
* Try out the STM32-for-VSCode plugin??


Plugins to install:
* STM32-for-VSCode
* cortex-debug



## Viewing Peripherals
* An '.svd' file is required to view the peripherals of the MCU
* Add an SVD file from this repo into the root directory of the folder
* Add this line into each configuration in `.vscode/launch.json`: `"svdPath": "${workspaceFolder}/STM32F446.svd",`

This will allow all the peripherals to be viewed.



# Profiling


# Testing

