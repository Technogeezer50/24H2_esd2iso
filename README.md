# 24H2_esd2iso 

## What is 24H2_esd2iso?

24H2_esd2iso is a utility to automate the creation of Windows 11 ARM 24H2 installation ISOs for use with VMware Fusion
on on Apple Silicon Macs.
This utility uses command line tools found in VMware Fusion 13.5 and later to download an ESD file from Microsoft and create the
installation ISO. 

> [!NOTE]
> VMware Fusion 13.6.1 fixed issues relating to the download of Windows 11 24H2 and proper creation of the ISO when
> using the "Get Windows from Microsoft" feature. This utility is no longer required as a workaround for
> problems found in VMware Fusion 13.6.0 and earlier. It remains available for those of you that want to automate the
> steps needed to download Windows 11 24H2 ARM ISOs from the macOS Terminal app (UNIX shell).

## Prerequisites 

* Apple Silicon Macs running macOS 13 or later.
* VMware Fusion 13.5 or later must be installed and located at /Applications/VMware Fusion.app.   

## Installation and Use 

* Download this project from GitHub: https://github.com/Technogeezer50/24H2_esd2iso. The latest released version
can be found in the "Releases" section on the right hand side of the project page. You can download either
the .zip or .tar.gz format file.
* Extract the downloaded file.
* Move or copy the file 24H2_esd2iso to a location of your choice (preferably an empty folder where you will build your ISO)
* Open the macOS Terminal app, and cd to the empty folder.
* Change permissions on 24H2_esd2iso to make it executable (it does not require root permissions).
* Run 24H2_esd2iso and follow all prompte.

## Known issues

24H2_esd2iso attempts to clean up after itself. In the event that a download of the ESD from Microsoft should fail
(and their servers have been a bit flaky lately), you should remove the partially downloaded ESD file if it exists before
rerunning the command.

Sorry, but there's no "restart interrupted network transfers from the point of failure" available for 24H2_esd2iso
like there is for w11arm_esd2iso. If the transfer doesn't complete, you'll need to wait for the entire ESD 
file to download again. Trying to keep things simple and not require open source utilities (such as 
aria2) means that the restart capability isn't available. 

## What's the difference between 24H2_esd2iso and w11arm_esd2iso?

Both have some similar heritage (and needs for their existence). The big differences are:

* 24H2_esd2iso only requires the installation of VMware Fusion. w11arm_esd2iso requires several
  open source utilities to be installed.
* 24h2_esd2iso injects the VMware vmxnet3 virtual network driver into the Windows installation ISO 
  (which makes it easier to go through the Windows OOBE setup as a network will be found). w11arm_esd2iso
  does not install any of the VMware drivers, so network drivers must be installed manually during the
  Windows Setup process.
* 24H2_esd2iso only works on Apple Silicon Macs. w11arm_esd2iso works on Macs and Linux (both Intel
  and ARM architectures).

## Licensing

22H4_esd2iso is Copyright (C) 2024 Paul Rockwell.

You may freely use and modify this utility for use in your own projects. If you do modify 24H2_esd2iso, please provide attribution,
and offer it with the same freedom to use as I've offered it you.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  

