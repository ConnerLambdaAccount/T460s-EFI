# T460s-EFI
![T460s](/README_Images/T460s.jpg)
Hackintosh High Sierra for Lenovo Thinkpad T460s <br />
Using Intel HD 520 Graphics, 256gb SSD, 1920x1080 Screen <br />
Works: (sleep, brightness keys, graphics, trackpad) <br />
Doesn't Work: ***NO SOUND***, integrated microphone, camera <br />
USB wifi required, install necessary drivers for your USB <br />

***Please commit if you can help with sound***

# USB Preparation (8 GB+)
- Open disk utility, select USB <br />
- Erase, Select MacOS Extended Journaled, GUID partition <br />
![Disk Utility](/README_Images/disk_util.png)
- Download High Sierra Installer, Through App Store or DosDude1's High Sierra Patcher (Sometimes store will download a useless 29 mb installer) <br />
DOSDUDE1 LINK: https://drive.google.com/file/d/1W992CqAjQa0A1gmWubnUeUarb4B4Jo-w/view <br />
- Open Terminal: sudo /Applications/Install\ macOS\ High\ Sierra.app/Contents/Resources/createinstallmedia --nointeraction --volume /Volumes/[YOUR USB] <br />
![Terminal](/README_Images/Term.png)
# Clover Custom Install Options
![Clover Select](/README_Images/Clover_select.png)
- MAKE SURE TO SELECT YOUR USB WHEN SELECTING LOCATION <br />

- Install Clover in the ESP <br />
- Clover for UEFI ONLY booting <br />
- (No drivers in this step, all are in the CLOVER.zip)
- Install RC scripts on target volume
![Clover End](/README_Images/Clover_end.png)

# Insert CLOVER folder
Once Finished, there should be an EFI partition on your desktop <br />
If not: <br />
- diskutil list <br />
Find EFI for your usb <br />
- sudo diskutil mount /dev/diskXsX <br />
EFI will be in Finder or on Desktop <br />

If/When there is:<br />
- Move CLOVER folder (in this repo CLOVER.zip) into EFI/EFI <br />

# Install through USB
- Plug in USB, Boot T460s, hit F12 on startup <br />
- In boot menu, boot from your USB <br />
- In Clover, boot the USB Installer<br />
- Once prompted, open disk utility, format drive as APFS w/ GUID if using an SSD, macOS Extended Journaled w/ GUID if using a HDD <br />
- Takes a while, once done, close with the red button, install MacOS to your target drive <br />
- Once done, screen will probably go black & reboot 3/4 through installer, its done installing <br />
- Boot the USB, in clover, select your target drive <br />

# Install Clover on Your Target Drive
- This is so you no longer need to boot with USB <br />
- Get clover installer pkg onto your computer, I did this through USB or ethernet <br />
- Install with the same options as the USB, this time to our target drive <br />
- Follow "Insert CLOVEr folder" but with the target drive instead of the USB <br />
