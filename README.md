# MRT-HelloCpp

## Preparations
To be able to easily use this project, the MRT-Environment must be set up first. Please clone it from its own repository and execute the installer script before continuing with this tutorial.

## Importing the project
  - To import the project, it is recommendable to create a folder *workspace* in the MRT-Environment folder. When you start Eclipse you can choose this filder as the workspace root.
  - Clone the MRT-HelloCpp project directly into this workspace folder
  - Choose *File/Import...* from the Eclipse Menu
  - Choose *Existing Code as Makefile Project* from the C/C++ category
  - Enter a project name (e.g. 'HelloCpp') and pick the location where you have cloned the project
  - As a Tool chain select *Cross GCC*
  - Press Finish 

## Compiling the project

The project is compiled using an automatically generated makefile. To be able to compile, the cross compilation tools must be available on to the build environment. 

- Select *Project/Properties* from the Eclipse menu.
- Select *C/C++ Build/Settings*
- In the tab *Tool Settings* select *Cross Settings*
- In the field *Path* enter the path to the *raspberrypi/tools/arm-bcm2708/gcc-linaro-arm-linux-gnueabihf-raspbian-x64/bin* folder of the MRT-Environment.
- Select *Project/Build Project* from the Eclipse menu. The project should build without errors.

## Remote debugging
Before this project can be debugged remotely, you need to do some preparations:

### Step 1: Prepare the Raspberry Pi

Create the path */home/pi/remote-debugging/* on the RapberryPi.
     mkdir /home/pi/remote-debugging/ && chmod 777 /home/pi/remote-debugging/
     
### Step 2: Create the remote system connection

  - In the eclipse menu, open *Window/Open Perspective/Other...*.
  - select *Remote System Explorer* (RSE).
  - Open the RSE perspective (upper right corner).
  - Define a connection to a remote system (first icon in the left panel).
  - In the new conncection assistant select *SSH Only*.
  - Press *Next* and enter the IP-address of you Raspberry Pi in the *Host* field. Note: the Raspberry Pi must be on the same network (try pinging it using the *ping* command from a console to verify).
  - In the *Name* field enter e.g. 'RemoteRPI'.
  - Switch back to the *C/C++* perspective.
    
### Step 3: Configure the run configuration
  - In the Eclipse menu, open *Run/Debug Configurations...*.
  - Select the *HelloAssembler Auto Remote Debug* configuration.
  - On the *Main* tab, in the *Connection:* field, choose the just created connection.
