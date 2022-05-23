# proton-script
A script to make it easier to manually execute programs in proton.
Script includes configuration file and 

# Using the script
Just run the script with a path to the executable, like `proton "/path/to/program.exe"` or proton `"C:\path\to\program.exe"`

# Config file
When executing the script it will create a proton.conf in ~/.config/proton.conf.
This file contains options like setting the working dir or disabling / enabling things like dxvk.
The config file can also be placed in the directory of the exe or you can specify it manually with CONF=/file/to/proton.conf

Also, any option set as variable will override the options from the config file.
For example: `DXVK=0 proton` will override the DXVK option from the config file.

The order in which the configuration file will be loaded:
```
  1 $CONF variable
  2 EXE-directory/proton.conf
  3 EXE-directory/.proton.conf
  4 Current Directory/proton.conf
  5 Current Directory/.proton.conf
  6 ~/proton.conf
  7 ~/.proton.conf
  8 ~/.config/proton.conf        (default)
  9 ~/.config/.proton.conf
```
