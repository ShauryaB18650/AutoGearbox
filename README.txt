***Use Autogear.sldprt (added in the commit called "added Autogear as a part" for single gears.***


Project Overview
This SolidWorks project utilizes a centralized equation system to automate the design of a four gear assembly. The geometry of all components is driven by a single external text file. Modifying the values in this text file updates the tooth profiles, diameters, and center distances of the entire assembly simultaneously.
\\
Input Parameters
The system requires the following inputs within the linked text file:
Global Module: Establishes gear tooth size.
1nTeeth, 2nTeeth, 3nteeth, 4nteeth: Sets the tooth count for each respective gear.
GlobalPressureAngle: Defines the contact angle for the involute profile.
\\
Computed Geometry
The model solves the following equations to maintain mechanical validity:
Pitch_Dia = Module * nTeeth
GearWidth = Module * 6
Dedendumm = Module * 1.25
Base_Dia = Pitch_Dia * cos(PressureAngle)
CircPitch = (3.1415926 * Pitch_Dia) / (nTeeth * 2)
FilletR = CircPitch / 8
\\
Assembly Automation
The assembly logic ensures that:
The circular pattern instances for teeth are linked to the nTeeth variable.
The shaft diameter and gear width update across all parts.
The distance between gear centers is calculated to maintain proper mesh.
\\
Usage Instructions
Open the .SLDASM file in SolidWorks.
Access the Equations tab from the Tools menu.
Click the Open File button located at the bottom of the Equations dialog.
Edit the required values within the .txt file.
Save the .txt file and close it.
Click the Rebuild button (traffic light icon) in SolidWorks.
The assembly and its constituent parts will resize and reposition automatically.
