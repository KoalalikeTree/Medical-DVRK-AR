# Medical-DVRK-AR
MRSD Class project

## Install and running Vrep/Coppelia
Download Edu version in your ubuntu version (Player version can't import a urdf file)
http://coppeliarobotics.com/ubuntuVersions

Extract it to your local folder

In your Ubuntu terminal
```sh
roscore
```

Source the setup.bash file so that later you can import files from your workspace to Vrep
* This step is crucial for importing urdf file *
```sh
source ~/.../your_work_space_name/devel/setup.bash
```

Open a new terminal and cd to the root directory of coppeliar, then run the .sh file. 
```sh
cd ~/coppeliar_edu
./coppeliaSim.sh
```


## Input URDF files (dvrk model) into Coppelia
You should already build your workspace and have dvrk-ros in your source folder
if not, please following the instruction on
https://github.com/jhu-dvrk/sawIntuitiveResearchKit/wiki/CatkinBuild

To get the URDF file, you need convert it through command line
```sh
cd ~/.../your_work_space_name/src/dvrk-ros/dvrk_model/model
rosrun xacro xacro both_psms.urdf.xacro > both_psms.urdf
```
You can convert other files too. You can see a new URDF file generated in the same folder

Then, in the Coppelia top bar, click 
plugin > URDF import > import > choose the generated urdf file

You should see the model dvrk robot and its joint hierachy appear in the scene


## Read the blaser Scene in Coppelia
Download Coppelia scene file from
https://github.com/biorobotics/blaser-vrep/tree/master/blaser-3.0
- blaser3.0.ttt	contains the model and code of blaser sensor
- blaser3.0_ur.ttt contains the UR5 and blaser

In coppelia:
Top bar > file > open scene > choose your .ttt file
