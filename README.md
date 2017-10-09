# DellEMC CS MDT Standard Client Task Sequence (boot in factory) project files

This repository contains everything you need to get started on a DellEMC factory enabled MDT project.  The information here pertains to an MDT "Standard Client Task Sequence" project which has "factory hooks" added to allow the majority of your task sequence to execute in the DellEMC factory, aka a "boot in factory" project.

## Essential documents (Mandatory)

### [Global Factory Imaging for MDT 2013 user guide external_EN_1215.pdf - the "User Guide" ](https://github.com/LairdBishop/CFI_MDT_Template/blob/master/Global%20Factory%20Imaging%20for%20MDT%202013%20user%20guide%20external_EN_1215.pdf)
***
You may hear this document referred to in short as the "User Guide" or the "White Paper" as you interact with your IMS engineer or project manager.  

**_Please invest the time to fully read and understand this document, which serves as the definitive guide for this type of project._**  The majority of media failures, project delays, factory exceptions and customer escapes we encounter can be traced to deviation from the user guide.

If you have any questions as you work toward implementation please reach out to your assigned IMS engineer who will be happy to assist. 

### [SCCM_MDT_IMS_TechSpec_5.1.doc - the "IMS TechSpec" ](https://github.com/LairdBishop/CFI_MDT_Template/blob/master/SCCM_MDT_IMS_TechSpec_5.1.doc)
** DO FIRST! This document must be completed fully and accurately at the outset of any project and returned to your IMS engineer and project manager. **

This document tells us everything we need to know to get your project and testing set up correctly.  Please take a few minutes to complete one document for each project (SI#).  If you have any questions please reach out to your assigned IMS engineer for assistance.

## Supporting files

### [DellCFI_Template.xml](https://github.com/LairdBishop/CFI_MDT_Template/blob/master/DellCFI_Template.xml)
***
This template is the Standard Client Task Sequence template from MDT with the "factory hooks" already integrated as prescribed in the [user guide](https://github.com/LairdBishop/CFI_MDT_Template/blob/master/Global%20Factory%20Imaging%20for%20MDT%202013%20user%20guide%20external_EN_1215.pdf). You can use this as the basis for a new task sequence (recommended), or just create a "dummy" task sequence from it and then copy and paste the factory hooks from it to your existing task sequence.

Once you place this file in [Deployment Share]\Templates folder, it will be available as a template the next time you create a task sequence in that deployment share.  Just select "Dell CFI Boot-In-Factory Task Sequence" from the dropdown.

### [hidewirelessetupinoobe_x64.txt](https://github.com/LairdBishop/CFI_MDT_Template/blob/master/hidewirelessetupinoobe_x64.txt)
***
The following line must appear in your Unattend.xml file to prevent an interactive scenario in the factory:
   "<HideWirelessSetupInOOBE>true</HideWirelessSetupInOOBE>"

This text file gives context.  Modify the Unattend.xml in [Deployment Share]\Control\[Task Sequence] folder to include this value.

### [CustomSettings.ini](https://github.com/LairdBishop/CFI_MDT_Template/blob/master/CustomSettings.ini) and [Bootstrap.ini](https://github.com/LairdBishop/CFI_MDT_Template/blob/master/Bootstrap.ini)
***
These files contain the entries shown on page 17 of the user guide. The values in these files must appear in the files associated with the media you will create to send to the factory, not the ones under your Control folder.  Having all of these values specified ensure a silent task sequence, which is required in the factory. Copy and paste any missing values to the rules file you associate with the generated media.

 
