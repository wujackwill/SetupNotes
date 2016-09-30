# [Notes on dual-booting GNU/Linux on Macbook 2009](#notes-on-dual-booting-gnu-linux-on-macbook-2009)

Rewrite/update based on Peter Upfolds article https://fosswire.com/post/2009/03/how-to-ubuntu-810-on-white-macbook/

This guide is incomplete and actively in progress.  I have only tested this on white macbooks from 2009.

# Table of Contents
* <a href="https://github.com/TechnologyClassroom/SetupNotes/blob/master/GNULinuxOnMacbooks.md#configuring-the-original-mac-os-x-10.6.8">Configuring the orignal Mac OS X 10.6.8</a>
* <a href="https://github.com/TechnologyClassroom/SetupNotes/blob/master/GNULinuxOnMacbooks.md#shrink-your-mac-installation-to-make-room-for-gnu-linux">Shrink your Mac installation to make room for GNU/Linux</a>
* <a href="https://github.com/TechnologyClassroom/SetupNotes/blob/master/GNULinuxOnMacbooks.md#download-and-install-refit">Download and Install rEFIt</a>
* <a href="https://github.com/TechnologyClassroom/SetupNotes/blob/master/GNULinuxOnMacbooks.md#create-a-livedvd-or-liveusb-with-a-gnu-linux-iso">Create a liveDVD or liveUSB with a GNU/Linux ISO</a>
* <a href="https://github.com/TechnologyClassroom/SetupNotes/blob/master/GNULinuxOnMacbooks.md#install-gnu-linux">Install GNU/Linux</a>
* <a href="https://github.com/TechnologyClassroom/SetupNotes/blob/master/GNULinuxOnMacbooks.md#if-the-grub-installation-fails-use-boot-repair">If the grub installation fails, use Boot-Repair</a>
* <a href="https://github.com/TechnologyClassroom/SetupNotes/blob/master/GNULinuxOnMacbooks.md#configure-ubuntu-studio">Configure Ubuntu Studio</a>

# [Configuring the original Mac OS X 10.6.8](#configuring-the-original-mac-os-x-10.6.8)

Skip this section if you have already setup your Mac for the first time.  The Macs I tested this on had never been used before.

* Brand new first run configuring the system
  * Choose your country (United States) > Continue
  * Choose your keyboard (U.S.) > Continue
  * Do not transfer my information now > Continue
  * Choose your wireless network and enter the password or connect through ethernet > Continue
  * (Optional) Enter your Apple ID and password > Continue
  * (Optional) Enter your registration details > Continue
  * Full Name change's the system name.  Make these details consistent across your network.  Account Name is the default admin account.  Write the password down.  > Continue
  * Choose from the picture library.  Choose a picture > Continue
  * Choose your time zone > Continue
  * Go

* Software Update box
  * Install
  * Agree

* Apple Icon > System Preferences
Note: On a Mac that is intended for use in educational environments, I would do more settings optimization in System Preferences.
  * Security
	* Firewall
	  * Click the lock icon at the bottom left to unlock
	  * Start
	* Click the < arrow at the top left.
  * Sharing
	* Change "Computer Name:" to something that makes sense for your organization.  For my macbooks I am using "cc003mb2009" as the scheme.  It is the lamest scheme I have come up with yet, but it is very accurate.  It allows for 999 macbooks from 2009.
	* Click the < arrow at the top left.
  * Accounts
	* Click the "+" plus sign.
	  * New Account: Standard
	  * Full Name: crew
	  * Account Name: crew
	  * Password: 
	  * Verify: 
	  * Password hint: The password is empty.
	  * Create Account
	  * OK
	  * Turn Off Automatic Login
	* (Optional) Change picture icon
	* Click the < arrow at the top left.
  * Click the red X at the top left to close System Preferences.

# [Shrink your Mac installation to make room for GNU/Linux](#shrink-your-mac-installation-to-make-room-for-gnu-linux)

* Boot Camp Assistant
  * Click on the magnifying glass in the top right.
  * Type "Boot Camp Assistant" and press enter or return.
  * Continue
  * I have the Mac OS X installation disc... > Continue
  * Click on the dot between the Mac OS X and Windows section.  Drag left until the Mac OS X section reads 30 GB.  > Partion
   * Note: This is the configuration I used for Macs OS installations that were not used and not intended to be used.  If you already have data, you can find out how much free space you have and decide how much you should use with the terminal command: df -h
  * Click on "Quit and Install Later" because we are not installing Windows.

# [Download and install rEFIt](#download-and-install-refit)

* rEFIt
  * Download the Mac disc image of rEFInd from http://downloads.sourceforge.net/refit/rEFIt-0.14.dmg?use_mirror=
  * Double click on rEFIt-0.14.dmg
  * Double click on rEFIt.mpkg
  * Continue
  * Continue
  * Agree
  * Install
  * Enter your admin password > OK
  * Close
  
# [Create a liveDVD or liveUSB with a GNU/Linux ISO](#create-a-livedvd-or-liveusb-with-a-gnu-linux-iso)

# [Shut Down the Mac](#shut-down-the-mac)

* Shut Down
  * Click on the Apple icon in the top left
  * Shut Down...
  * Shut Down

# [Install GNU/Linux](#install-gnu-linux)
Insert a liveUSB or liveDVD with GNU/Linux installed.  I am using Ubuntu Studio 16.04.1 64 bit on a DVD.
Press the power button.
Wait just a moment until the chime sound.  Hold the alt or option key until you see a menu.  If you boot into Mac OS X.  Shut down and try again.
Click EFI Boot.
Click the arrow under EFI Boot.
"Try Ubuntu Studio without installing" should be highlighted.  Hit the enter or return key.  Be patient while the system loads.  It takes longer to load an entire operating system to RAM from a DVD or USB than it normally does to boot a system.
Double click "Install Ubuntu Studio 16.04..."
Choose your language > Continue
Continue
Continue  Note: if you are only intending to do audio production, uncheck the rest of the boxes that do not have to do with audio.  Otherwise, leave them all checked.
Something else > Continue
Click on "/dev/sda3 fat32" and click the "-" minus sign.
Click on "free space" at the bottom and click the "+" plus sign.
Change the "Mount point:" to "/" from the drop down menu.
OK
Change "Device for boot loader installation:" to "/dev/sda3" from the drop down menu.
Install Now
Continue
Continue
Choose your time zone (New York) > Continue
Choose your keyboard layout (English (US) English (US)) > Continue
For the "Your name:" entry, choose a username for your admin account.  The installer will automatically format it into an acceptable format below.
For the "Your computer's name:" entry, pick the same scheme as you did on the Mac operating system above.
Choose a standard password for your admin account.
--missing radio choice
--missing button name
Wait a long time for the system to be installed.

# [If the grub installation fails, use Boot-Repair](#if-the-grub-installation-fails-use-boot-repair)
Due to a bug in the ubiquity installer, it may read "GRUB installation failed The 'grub-efi-amd64-signed' package failed to install into /target/. Without the GRUB boot loader, the installed system will not boot." That is serious, but do not worry. We can fix it in the next section > OK

The installer may crash after that with "Installer crashed Installer crashed We're sorry; the installer crashed. After you close this window, we'll allow you to file a bug report using the integrated bug reporting tool. This will gather information about your system and your installation process. The details will be sent to our bug tracker and a developer will attend to the problem as soon as possible" > Close Click on the Ubuntu Studio icon in the top left.  Click on Terminal Emulator.  Type in "sudo pkill ubiquity" without quotes and press enter or return.

  * Connect to the Internet through an ethernet wire or through a wifi device that is supported by the Linux kernel.
  * Install Boot-Repair
   * Boot from a ubuntu based distribution.  Enter these commands and follow the directions:

    sudo add-apt-repository ppa:yannubuntu/boot-repair -y
<!-- verify the -y switch works and remove the enter key. -->
   * Press the enter or return key to continue adding the repository

    sudo apt-get update
    sudo apt-get install -y boot-repair

  * Run Boot-Repair
   * In a terminal, run this command:

    boot-repair

   * (Optional) Click on the "Advanced options" arrow.  Click on the "Other options" tab.  Uncheck the "Upload the report to a pastebin" and "Participate to statistics of use" boxes.  Click on the "Advanced options" arrow to collapse the menu.
   * Click on the "Recommended repair (repairs most frequent problems)" button.
   * Follow all of the directions it gives.  Click on the "Forward" button after you have completed each action.  When I ran the Boot-Repair, I ran 3 commands, Forward, 1 command, Forward, No, OK, and I closed the logfile.

# [Shut Down the liveDVD or liveUSB](#shut-down-the-livedvd-or-liveusb)

* Click on the Ubuntu Studio icon in the top left.
* Click on the power icon in the drop down menu.
* Click on the "Shut Down" button.  If you are using a DVD, it will eject and ask you to press the enter key.

# [rEFIt can now be uninstalled](#refit-can-now-be-uninstalled)
* The first time I rebooted, the computer booted straight to grub.  The second time I booted, rEFIt loaded.  ???  In the rEFIt menu, you can only use the arrow keys and the enter or return key.  Select "Boot EFI\ubuntu\grubx54.efi from EFI" to load the grub menu and Ubuntu Studio.  Select "Boot Mac OS X from 10.6" to directly load Mac OS.

# [Configuring Ubuntu Studio](#configure-ubuntu-studio)

* Connect to the Internet through an ethernet wire or through a wifi device that is supported by the Linux kernel.

* Incomplete Language Support window
 * Click on the "Run this action now" button.
 * Click on the "Install" button.
 * Enter your password.
 * Wait for it to finish.
 * Click on the "Close" button.  Click on the "Close" button.
 

* (Optional) Install wireless drivers through the Additional Drivers GUI
  * The Macbook I used had proprietary drivers available.
  * Click on the Ubuntu Studio menu at the top left.  Type in "Additional Drivers" without quotes
  * Click on the "Using ____ wireless driver source from _____ (proprietary)" option to use a proprietary driver.
  * Click on the "Apply Changes" button
  * Click on the "Close" button.
  * Reboot and you can unplug the ethernet wire or through a wifi device.

* (Optional) Install wireless drivers through the CLI

http://askubuntu.com/questions/22118/can-i-install-extra-drivers-via-the-command-prompt

* Upgrade the system

sudo apt-get update && sudo apt-get upgrade -y

* Install more software

sudo apt-get install -y lxde-core awesome leafpad python-pygame idle-python2.7 git puppet xaos cowsay fortune bb feh libaa-bin caca-utils aview figlet sl telnet xfonts-mona xfonts-terminus xfonts-100dpi xfonts-75dpi xfonts-base screenfetch

* Install Processing

wget http://download.processing.org/processing-3.2.1-linux64.tgz
--missing install line
* Create a Desktop icon for processing
http://askubuntu.com/questions/299052/how-to-execute-sh-script-from-a-desktop-shortcut

* Configure users

* Configure browser preferences