DellCFI_Template.xml
---------------------
Place this file in [Deployment Share]\Templates


hidewirelessetupinoobe_x64.txt
------------------------------
The following line must appear in your Unattend.xml file to prevent an interactive scenario in the factory:

<HideWirelessSetupInOOBE>true</HideWirelessSetupInOOBE>

This text file gives context.  Modify the Unattend.xml in [Deployment Share]\Control\[Task Sequence]


CustomSettings.ini and Bootstrap.ini
------------------------------------
The values in these files must appear in the files associated with the media you will create to send to the factory, not the ones under your Control folder.  Having all of these values specified ensure a silent task sequence, which is required in the factory. 

(Note - CSWin8 can be removed or set to false if not Windows 8 or 8.1)