# Win7-on-modern-hardware
Run Windows 7 on modern hardware!

I made this guide, my laptop dosen't support windows 7 drivers and stuff so it might not work for you.

⚠️ Mandatory Disclaimer By continuing, you acknowledge that you have read and understood the contents of the following disclaimer, and consent to their terms.

The process described in this document could cause irreversible damage to your laptop, and you should prepare yourself for that outcome before you begin. I accept absolutely no responsibility for the consequences of anyone choosing to follow or ignore any of the instructions in this document, and make no guarantees about the quality or effectiveness of the software in this repo.

PREREQUISITES:

Rufus

A Windows 7 ISO (You can download one from the releases section if you are using x64 architecture.)

A CSM-compatible BIOS and motherboard (this can be skipped but will need to be patched with UEFISeven.)

An 8GB-minimum USB Drive

The Windows 7 Image Updater by Atak_Snajpera https://forums.mydigitallife.net/threads/windows-7-image-updater-skylake-kabylake-coffelake-ryzen-threadripper.76335/ (Important!)

Step 1. Create the patched ISO.

Using the Windows 7 Image Updater, select your downloaded Windows 7 image. it is VERY much important that you select every option in the tool except the "Shutdown the PC when finished" option.

This can take 3-5 hours or more if your PC is a low end Desktop/Laptop. Mine is a low end laptop even though it is a mobile workstation, anyways mine took about 7 hours.

Step 2. Prepare USB drive

Using Rufus, prepare your USB drive under these settings:

MBR, (BIOS or UEFI-CSM) OR GPT, (BIOS or UEFI)  and set the file system as NTFS. Set your image as the output of the previously mentioned tool, NOT the original ISO. After completing, reboot into your BIOS.

Step 3. Prepare BIOS

This part is very important and also the most common cause of issues. If you did not do the previous steps properly, or do not do this one properly, when loading the setup ("Starting Windows") it will either blue screen or freeze. So make sure to read carefully: For this you will need to enable CSM support in your BIOS or skip it and we'll patch it. 
Every motherboard is different, even across the same manufacturer, so for this you will have to use your intuition to figure out where exactly, or look up your specific model and how to enable it. 
I have to be somewhat generic with this step due to motherboard variations. You will also need to disable secure boot, otherwise you likely will not even reach "Starting Windows".

Step 4. Boot into your USB drive. Note: if you chose to use UEFI, you will need to follow https://github.com/manatails/uefiseven's instructions.

Step 5. Commands and Installation

After you booted into the Installer. Press Shift+F10

Now type "select <disk you're installing to>". Then, type "clean". This will completely format the drive and remove all of its contents. Next, type "convert GPT". Finally, type exit twice and reboot your computer.
When loading back into the installer, install to the cleaned drive as normal.

You should be done!

Credits: 

https://forums.mydigitallife.net/members/atak_snajpera.1020956/ (for creating the ISO.)

https://github.com/manatails/uefiseven (For patching the Installation to support UEFI.)

https://microsoft.com  (Microsoft for creating this Windows 7 OS.)
