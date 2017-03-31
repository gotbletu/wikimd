# Wii Softmod
Softmod any Original Wii Console using Letterbomb hack

### general information for buying a used wii
*Info: Sometimes buying locally on Craigslist or Offerup, people dont take good pictures or include much information, so if you need to buy a wii with gamecube ports, look for the RVL-001 and usually Standing Wii logo*

- Wii with Gamecube Controller Ports: Model **RVL-001**
- Vertigo Wii logo or including a Wii Stand has GameCube ports >> [Example](http://s24.postimg.org/eluua2r0l/Wii.jpg)

### hardware requirements

- Wii Console
- Wiimote Controller (Best to use the non motion plus remote)
- SD/SDHC Card (It will be in the Wii at all times, use older SD card for best compatibility)
- SD Card Reader for PC
- External 2.5inch USB HDD


### find Wii version and MAC Address (from Wii)
*Info: We need this information to do the LetterBomb hack to install homebrew channel. Most USA version is 4.3U, if not update your Wii*

- system version: **Wii > Wii Options > Wii Settings**
- mac address: **Wii > Wii Options > Wii Settings > Page 2 > Internet > Console Information**


### prepare the LetterBomb Hack (from PC)

- Format SD Card to FAT32
- Go to https://please.hackmii.com/
- Fill in Wii Version and Wii Mac Address
- Checkbox Bundle the HackMii Installer for me!
- Hit Cut the blue wire
- It will download LetterBomb.zip > Extract the **contents** only to the root of the **SD Card** (use **rsync** to be sure)
 

    Extracted content to SDCard example:
    
    SD:/APACHE-2.0.txt
    SD:/CREDITS.txt
    SD:/LICENSE.txt
    SD:/README-BootMii.txt
    SD:/README-HBC.txt
    SD:/README.txt
    SD:/boot.elf
    SD:/private

### install homebrew channel/bootmii (from Wii)
*Info: Homebrew channel allows you to install other hacked apps on the Wii, BootMii allows you to backup your Wii nand incase you brick your wii, you will need this*

- Take SD Card and Insert into Wii Console
- Wii > Mail > Today > LetterBomb
- LetterBomb > Hit 1 > Continue > hit A > Install The Homebrew Channel > Yes, Continue > Continue
- LetterBomb > Hit 1 > Continue > BootMii > hit A > Prepare our SD Card > Install BootMii > Exit

### backup Wii nand and key file using BootMii
*Info: BootMii allows you to backup your Wii nand file incase you brick your wii, you will need this to recover. It will take a while to backup, the file is around 500MB+*

- Wii > Homebrew Channel > hit Home Button > Launch BootMii
- **(Power = right, Reset = OK)** WiiMote will not work
- BootMii > Gear Icon (4th Icon) >  Green Arrow Backup Nand Icon (1st Icon)> Wait for it to Finish
- It still start creating nand file, then verify it (should take about 10-15mins)
- Hit **Reset** button to exit
- Power down, **nand.bin** and **keys.bin** will be saved on SD card, transfer that to PC for safe keeping

### install cISO
*Info: The cIOS (custom IOS) is a custom piece of software that is used by some applications that work with unofficial content.
By installing it, you can for example use Backup Loaders and install unofficial channels to your Wii menu.
Every cIOS uses an official IOS by Nintendo as its base*

- Enable internet wifi connection on Wii
- Download the Wii cISO files: [Here](https://sites.google.com/site/completesg/backup-launchers/installation/d2x-cIOS-Installer-Wii.zip?attredirects=0&d=1)
- Extract it to **SDCard:/apps/d2x-cIOS-Installer-Wii**
- Put SD Card into Wii
- Wii > Homebrew Channel > d2x-cIOS-Installer > Load
- **WARNING 1: DO NOT PRESS A UNTIL YOU ARE SURE**
- cISO: **v10-beta53-alt**
- cISO base: **56**
- cISO slot: **249**
- cISO revision: **21010**
- Hit A to continue, 249 should be blinking > hit A > It will download files from the internet, Wait for it to finish > Hit A
- It will return to the previous screen, next apply the following settings
- **WARNING 2: DO NOT PRESS A UNTIL YOU ARE SURE**
- cISO: **v10-beta52**
- cISO base: **57**
- cISO slot: **250**
- cISO revision: **65535**
- Hit A to continue, 250 should be blinking > hit A > Wait for it to finish, It will download files from the internet > Hit A
- Hit B to exit > You are done

### install priiloader
*Info: Priiloader (based on the app Preloader) is an app that replaces the first part of the system menu that gets booted. Like this it is able to load before the actual Wii menu appears on the screen.*

- Download the priiloader files: [Here](https://sites.google.com/site/completesg/system-hacks/priiloader/priiloader.zip?attredirects=0&d=1)
- Extract it to **SDCard:/apps/priiloader**
- Put SD Card into Wii
- Wii > Homebrew Channel > Priiloader > Load > hit A > hit + to install
- Note: It should now reboot in the Priiloader menu. If it doesn't, power off the Wii manually, then power it back on and **hold reset** while it's booting until you see it.
 
### install Nintendont [Play Gamecube ISO Games]
*Info: Allows us to play Gamecube iso/gcm games from external hard drive, requires Gamecube controller or compatible gamecube controller*

- Download the Nintendont files: [Here](https://sites.google.com/site/completesg/backup-launchers/gamecube/nintendont)
- Extract it to **SDCard:/apps/nintendont**
- Put SD Card into Wii and test it out
- Wii > Homebrew Channel > Nintendont > Load


*>>> Reset and Quit Game*
- Reset Game: R + Z + Start
- Quit/Exit Game: R + Z + B + Down

### where to put Gamecube games?
*Info: Gamecube games will only work on a __FAT32 Filesystem__*
https://sites.google.com/site/completesg/backup-launchers/gamecube/nintendont


Nintendont uses these paths:
- SDCard:/games/
- USB:/games/
- USB:/games/Name of game [GameID]/game.iso
- USB:/games/Legend of Zelda the Wind Waker [GZLP01]/game.iso

*>>> If the game has __multiple discs__, you can place an additional __disc2.iso__ in the same folder. Nintendont will "swap" discs automatically for you.*

- USB:/games/Resident Evil 4 (USA) [G4BE08]/game.iso
- USB:/games/Resident Evil 4 (USA) [G4BE08]/disc2.iso

### install USB Loader GX [Play Wii WBFS Games]
*Info: Allows us to play Wii WBFS games from external hard drive*

- Download the USBLoaderGX files: [Here](https://sourceforge.net/projects/usbloadergx/)
- Extract it to **SDCard:/apps/usbloader_gx**
- Put SD Card into Wii and test it out
- Wii > Homebrew Channel > USB Loader GX > Load

*>>> set USBLoaderGX default Gamecube loader to Nintendont*

- Wii > USBLoaderGX > Settings > Global Settings > Loader Settings > Gamecube Source > Auto
- Wii > USBLoaderGX > Settings > Global Settings > Loader Settings > Gamecube Mode > Nintendont
 
### where to put Wii games?
*Info: Since Gamecube games will only work on a __FAT32 Filesystem__, it is recommended that Wii games should use FAT32 also to be compatible*

USBLoaderGX uses these paths:
- USB:/wbfs/
- USB:/wbfs/Name of game [GameID]/GameID.wbfs
- USB:/wbfs/Donkey Kong Country Returns (NTSC) [SF8E01]/SF8E01.wbfs

*>>> FAT32 has a size limit of 4GB per file, so for Wii games that are too big, it has to be split into parts. In most cases splitting 4GB works fine, but on some games like Super Smash Bros Brawl, you want to split it  2GB instead.*

- USB:/wbfs/Super Smash Bros Brawl (NTSC) [RSBE01]/RSBE01.wbf1
- USB:/wbfs/Super Smash Bros Brawl (NTSC) [RSBE01]/RSBE01.wbf2
- USB:/wbfs/Super Smash Bros Brawl (NTSC) [RSBE01]/RSBE01.wbf3
- USB:/wbfs/Super Smash Bros Brawl (NTSC) [RSBE01]/RSBE01.wbfs

### fix black and white Wii games?
*Info: some PAL games will be grey color, this is due to it not being the same resolution as NTSC TV*

- Wii > USBLoaderGX > [Pick Wii Game] > Settings > Video > Force NTSC

### set USB Loader GX as the default startup Wii program
*Info: Make Wii autoboot into USBLoaderGX on startup*

- Run Priiloader (by holding the RESET button while the Wii boots.)
- Priiloader > Load/Install File > [Select USB Loader GX Dol] > Press A > Wait for Install > Return to Main Menu
- Priiloader > Settings > Autoboot > Installed File
- Priiloader > Settings > Return to > Autoboot
- Save Settings then hold power button on the wii to poweroff
- Start the wii again, it should boot straight into USB Loader GX



### Using Wii Backup Fusion (from Linux)
*Note: allows you to convert Wii Roms to WBFS image or Gamecube Roms to ISO*

- install **wit** package from offical repository
- Download the WiiBackupFusion tar.bz2 files: [Here](https://sourceforge.net/projects/wiibafu/files/Wii%20Backup%20Fusion%201.1/)
- WiiBackupFusion > Options > Settings > WIT > Path to WIT: [/usr/bin/wit]
- WiiBackupFusion > Options > Settings > WIT > Path to titles: [/usr/share/wit]
- [How to use WiiBackupFusion](https://www.youtube.com/watch?v=8B2JOnFE5kM)


### disable wii standby mode
*Info: We want to poweroff the Wii and External 2.5inch Hard Drive, else the Hard Drive will still be on. (red led = poweroff ; yellow led = standby)*

- Wii > Wii Options > Wii Settings > Page 2 > WiiConnect24 > Standby Connection > Off


### different formats meanings
A PLAIN ISO file stores the content of the DVD byte by byte. It has a usual size of 4.7 GB. Most WBFS and ISO tools are able to detect unused areas (=holes) and fill them with a zeros. This method is called scrubbing. There are 4 classic formats:
- PLAIN ISO (1:1 copy)
- CISO (Compressed ISO, ignore unused blocks)
- WBFS (Multi ISO container, ignore unused blocks)
- WDF (Wii Disc File, mange holes directly)



### references
- https://sites.google.com/site/completesg/hacking-guide
- https://sites.google.com/site/completesg/hacking-guide/4-3-guide
- https://sites.google.com/site/completesg/how-to-use/bootmii
- https://sites.google.com/site/completesg/backup-launchers/installation
- https://please.hackmii.com/
- https://gbatemp.net/threads/wia-wii-iso-archive.250617/
- https://answers.yahoo.com/question/index?qid=20130701112716AA3h7Hf
- https://www.youtube.com/watch?v=6Hk5OHYD3Ic
- http://i.imgur.com/fGn0BXA.png
- http://wit.wiimm.de/
- https://sourceforge.net/projects/wiibafu/
- https://sourceforge.net/projects/usbloadergx/
- https://sites.google.com/site/completesg/backup-launchers/gamecube/nintendont
- https://www.reddit.com/r/WiiHacks/comments/3kqxz2/quitting_nintendontr_z_b_dpad_down_works_great/


### contact

                 _   _     _      _
      __ _  ___ | |_| |__ | | ___| |_ _   _
     / _` |/ _ \| __| '_ \| |/ _ \ __| | | |
    | (_| | (_) | |_| |_) | |  __/ |_| |_| |
     \__, |\___/ \__|_.__/|_|\___|\__|\__,_|
     |___/

- http://www.youtube.com/user/gotbletu
- https://twitter.com/gotbletu
- https://plus.google.com/+gotbletu
- https://github.com/gotbletu
- gotbletu@gmail.com

