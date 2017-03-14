# Xbox Softmod (Original Xbox Classic Console)
Softmod using exploited gamesave hack, allows to install emulators and play backup ISO games
* tutorial video: [Link](https://www.youtube.com/user/gotbletu)
* offical website: [Link](https://www.youtube.com/user/gotbletu)

### hardware requirements
- original xbox
- splinter cell game (black label only)
- xbox memory card
- xbox gameshark memory card to usb adapter
- xbox controller (1st party not generic shit)
- updater game (if Dashboard is below D:1.00.**5960**.01)
  - http://xbmcxbox.blogspot.com/p/dashboard-5960.html

### software requirements (using linux)
*Note: I dont run windows or 32bit system anymore*

- virtualbox with USB support (**virtualbox-ext-oracle**)
- make sure to add yourself to **vboxusers** groups
- install windows xp 32bit on virtualbox
- xbox action replay software and drivers for windows
- Softmod Installer Deluxe Final 5.11.zip (SID511.Installer.zip & SID511.Loader.SplinterCell.NTSC.zip)

### verify dashboard version is up to date
- Xbox Dashboard > Settings > System Info
- Wait for it to scroll down
- It should be version D:1.00.**5960**.01 (if not you need an updater game, see the list (http://xbmcxbox.blogspot.com/p/dashboard-5960.html)

### transfer softmod files to xbox memory card
- plug in xbox gameshark adapter with memory card to the PC
- start **windows xp 32bit virtualbox**, right click on the **USB icon** at the bottom of the Windows XP virtualbox screen, select **MicrosoftCrop XboxDevice**
- install xbox action replay software and drivers
- start xbox action replay software
- extract Softmod Installer Deluxe Final 5.11.zip
- drag and drop **SID511.Installer.zip** & **SID511.Loader.SplinterCell.NTSC.zip** into the Memory card field of the xbox action replay screen
- it should take about **5-10mins**, once done just close the software and remove the memory card

### transfer memory card files to xbox hard drive
- start xbox
- plug in memory card to the controller slot
- delete any existing saves or files on your xbox hard drive: **Xbox Dashboard > Memory > [Select Hard Drive Unit]**
- Go To Memory Card: **Xbox Dashboard > Memory > [Select Memory Card Unit]**
- hit **right analog** on the **SID511 Installer**, then **hit A > Copy**
- hit **right analog** on the **SID511 Loader SplinterCell NTSC**, then **hit A > Copy**
- done, now verify the files are copy to the hard drive then **remove the memory card**

### install softmod to xbox
*Info: Installing softmod with UnleashX Dashboard Interface then backup eeprom key and MS dashboard*

- put in the Splinter Cell game (black label only)
- Splinter Cell > Start Game > Linux > Check Points **(Softmod Installer Deluxe will start now)**
- Softmod Installer Deluxe > Backup / Restore Features > **Create Eeprom Backup** > Backup Eeprom
- Softmod Installer Deluxe > Backup / Restore Features > **Create Eeprom Backup** > **Move Eeprom to E** > Yes
- Softmod Installer Deluxe > Backup / Restore Features > **Create MS Backup** > Yes > OK
- Softmod Installer Deluxe > **Install Dual Boot Softmod** > Hacked Dash / **MS Dash** > Virtual C+Eeprom for **HD** > Install **UnleashX** Dashboard > Yes
- Eject Splinter Cell Game Disc (It might reboot the system quickly)
- If it does not reboot into the UnleashX program to continue installing then **Manually poweroff and then on the xbox**
- It will Finish the final installation once it resets itself, then **you are done with the softmod**

### enable FTP access ( change Static IP to DHCP )

- Connect Cat5 Ethernet Cable to the Xbox from Router
- Xbox UnleashX Dashboard > System > Boot Softmod Menu > Settings > Network > Type > hit A > **DHCP** > Save and Exit
- Xbox UnleashX Dashboard > System > Boot Softmod Menu > Reset Network > You will get a new DHCP IP Address
- Xbox UnleashX Dashboard > System > Boot Softmod Menu > Restart Xbox

### connecting to Xbox via FTP

- Install Filezilla
- user: xbox
- pass: xbox
- port: 21

# remove Clock Capacitor
*Note: This is a known issue, the xbox capcitor will leak over time. This is what will happen if you dont remove it* ![alt text](https://i.imgur.com/uPbGSn3.jpg)

- Model 1.0-1.5 (Remove it right away, does not require a replacement capacitor)
  - model 1.4 clock capcitor location (C7G2/C7G3) ![alt text](https://i.imgur.com/WniuNpG.jpg)
- Model 1.6 (Gold color capacitor, some say you dont need to remove since this is a pretty good capacitor that usually does not go bad overtime. If you do want to replace it, you need to replace the capacitor with another one) ![alt text](https://i.imgur.com/OWMDzLY.png)

# upgrade Xbox to a bigger Hard Drive via XboxHDM IDE DVD Drive method
*Info: I have an Xbox 1.6 model, I try the hotswap chimp method but it never worked, it always says OK, OK, Starting then its stuck at that screen forever after entering FATX in chimp2.4, 2.6, 2.61811, 2.61812. So that is why I am using XboxHDM on a PC, which works really well if you have all the hardware and software requirements*

### requirements
- PC with motherboard that has IDE port >> [Example](http://images.slideplayer.com/27/9012226/slides/slide_4.jpg)
- 1 IDE ribbon with 3-way connectors (1 for mobo, 1 for HDD, 1 for DVDROM) >> [Example](http://ecx.images-amazon.com/images/I/41TcYfNpitL._SX355_.jpg)
- IDE DVDROM Drive (SATA wont work with XboxHDM 1.9, **you can hookup the Xbox IDE DVDROM Drive to PC if you do not have a IDE DVD Drive already**) >> [Example](http://ep.yimg.com/ca/I/itwinkle_2271_230205968)
- Download XboxHDM 1.9 Software (Xbox Hard Drive Maker) [here](http://www.theisozone.com/downloads/xbox/tools/xbox-hard-drive-maker-v19-xboxhdm/)

### create XboxHDM disc
- **Create eeprom backup again and move to E:** Xbox UnleashX Dashboard > System > Boot Softmod Menu > Backup / Restore Features > Create Eeprom Backup > Backup Eeprom > **Move Eeprom to E** > Yes
- It will be saved to **E:\Backup\Eeprom**
- Download and Extract **XboxHDM 1.9 (Xbox Hard Drive Maker v19):** [here](http://www.theisozone.com/downloads/xbox/tools/xbox-hard-drive-maker-v19-xboxhdm/)
- on Linux PC: Open a terminal (going to extract and delete un-needed folders)


        $ cd ~/Downloads
        $ atool -x xboxhdm_v1.9.zip
        $ cd ~/Downloads/xboxhdm/linux
        $ rmdir C/ E/


- FTP into Xbox: copy the **C and E** folders into your PC **~/Downloads/xboxhdm/linux/**
- FTP into Xbox: copy the eeprom key to your PC (should be in **E:\Backup\Eeprom\\**) to **~/Downloads/xboxhdm/linux/eeprom/**
- on Linux PC: Open a terminal (create an iso image with your personal xbox eeprom key)


        $ cd ~/Downloads/xboxhdm
        $ chmod +x make-iso-lin.sh
        $ ./make-iso-lin.sh


- Use any Burning Program: Burn **linux.iso** we just created with XboxHDM at 4x slow speeds
- Since I didnt have a regular PC IDE DVDROM Drive, **I had to use the Xbox DVD Drive**
- **Put in the XboxHDM Disc we just burn into the Xbox DVD Drive**
- **To avoid the Xbox from auto shutting off** when we use its DVD Drive on our PC. We have to boot the Xbox up with everything connected in working condition, then **pull out the IDE cable from the DVD drive while the Xbox is still running** and then hook that up to the IDE Cable that is coming out from your PC. **Do not poweroff the Xbox** since we need it to keep power to the DVD Drive.
- **Disconnect all your hard drive on your PC that is not going to be used to format**
- Make sure the jumper is set to Master on your Hard Drive
- Connect the 3-way IDE Ribbon Cable from the PC motherboard to the Hard Drive then to the Xbox DVD Drive
- Power on your PC (**Note: Make sure IDE is NOT disable in your BIOS**, some people disable since it is old)
- Wait for the Disc to boot into XboxHDM, if not, you might have to hit **F12** to get the boot menu then just select CD or DVD drive
- At XboxHDM:


        # unlock xbox hdd (dont need to do this if is a new hdd with no xbox software on it)
        $ 3
        $ unlockhd -a
        $ reboot

        # build new hard drive from
        $ 1
        $ xboxhd
        $ yes (type yes to every prompt, there is going to be a few of them)
        $ 8 (to quit)
        $ reboot

        # lock xbox hdd (need to lock the hdd else it wont work on xbox)
        $ 3
        $ lockhd -a
        $ halt
        - Manually press/hold the power button on your PC to shutdown
        - Power off the Xbox Console also


- **You are done with building your New Hard Drive for Xbox**. Put in your new Hard Drive into your Xbox and test if it works.
- Not sure why but I had to **redo the softmod again** to get UnleashX Dashboard
- Make sure to enable FTP via **DHCP** on the xbox as well

### partition the new Hard Drive

- Since we have a bigger Hard Drive now we are going to partition it to use all the space.
- Download and Extract XBPartitioner 1.3 [here](http://www.theisozone.com/downloads/xbox/homebrew-apps/xbpartioner-13/)
- FTP into Xbox: put **XBpartitioner-1.3 folder** into **E:\Apps\XBpartitioner-1.3\\**
- reboot the xbox
- Xbox UnleashX Dashboard > Applications > XBpartitioner
- **Press A a few times** to expand the partition scheme until see **0 Free Space left** at the bottom
- **Press Start** to partition
- **Press Y** to confirm, it will format partition now
- **Press Back then B ** to exit and quit
- It will reboot
- Now check your Hard Drive Space on the UnleashX Dashboard. C: E: F: Drives should be different


### adding original xbox games ISO to the xbox
- install **extract-xiso** package >> [How to use extract-xiso](https://www.youtube.com/watch?v=GA3Aef6U-Zo)
- extract-xiso GTA.iso
- FTP into XBOX: copy games into **F:\games or E:\games** folder

### adding emulators to the xbox
- FTP into XBOX: copy roms into **F:\emus or E:\emus** folder ***[1.6 model]***
- FTP into XBOX: copy roms into **F:\Emulators or E:\Emulators** folder ***[1.0 model]***
- FTP into XBOX: copy roms into **F:\Apps or E:\Apps** folder ***[TSOP xbox]***
- FTP into XBOX: copy roms into **F:\games or E:\games** folder ***[TSOP xbox]***
- Note: on **Softmodded Xbox > UnleashX Dashboard > Emulators**
- Note2: on **TSOP Xbox > Xbox Admin > Applications**
- Which Emulators to use? http://xbmcxbox.blogspot.com/2013/03/complete-list-of-emulators-for-original.html
  - Super Nintendo: ZsnexBox
    - This is a port of the Zsnes Super Nintendo emulator to original Xbox by Nes6502, this emulator has a ton of features including preview videos,cheats database,720p/1080i hd options.The last release was version 3.6 and this for many is the best snes emulator on original Xbox
  - Nintendo: FCEUltraX
    - FCE Ultra NES is a FDS "Famicom Disk System" NES "Nintendo Entertainment System" for original Xbox.
  - Sega Genesis: NeoGenesis
    - NeoGenesis Sega Genesis/Megadrive/32X/SegaCD/MegaCD Emulator. This emulator able to play the original Sega CD game discs right from the original Xbox DVD drive.
  - Gameboy: XBoyAdvance
    - GameBoy Advance (GBA), Game Boy Color (GBC), original Game Boy (GB) / Super GameBoy (SGB) / Super Game Boy 2 SGB2 Emulator for original Xbox.
  - Nintendo 64: Surreal64
    - Surreal 64 is a Nintendo 64 Emulator for the original Xbox which combines three Windows based Nintendo 64 emulators that have been ported to the Xbox. These emulators are 1964, Project64 and UltraHLE.
    By porting three emulators we aim to improve the overall compatibility of the emulator.
  - Sony PlayStation: PCSXBox
    - A port of the PCSX emulator to Xbox. It emulates the Playstation 1 (PSX, PS1) console.
  - Neo-Geo: NeoCD/SDLx
    - NeoCD/SDLx is a original Xbox port of the NeoCD/SDL neogeo CD emulator. It is capable of running many original Neogeo CD games. Original Xbox port based on v0.20 sources
  - TurboGrafx-16: MednafenX-PCE
    - This is an PC-Engine/TurboGrafx-16/SuperGrafx/Arcade Card CD/CD/SCD emulator for the original Xbox ported from mednafen.
  - Sega Master System: Dega X
    - Dega X is an Sega Master System / GameGear Emulator for the Original Xbox
  - Killer Instinct XXX
    - KIxxx (Killer Instinct XXX) is an ultra 64 (yes the arcade one) emulator for original Xbox, it only emulates Killer Instinct 1 and Killer Instinct 2. It is based on U64x from Lantus which is based on U64PC. This is the recommended and more popular emulator to play Killer Instinct 1 & 2 on the original Xbox.- 
  - 
    - 
  - 
    - 

### xbox filename length limit
- 42 characters including extension
- no comma, plus signs
- vidir to rename
- vim :set colorcolumn=52

# TSOP Modded Xbox 1.0-1.5 Only
*Note: The reason we need to solder these joints is to disable write protection, thus allows us to flash the TSOP with something else*
- Requirements:
  - Soldering Iron & Solder tin & Flux
  - PC with DVD Burner
  - Hexen Boot Disc ([Download](http://www.theisozone.com/downloads/xbox/tools/hexen--shamblesedit--tk-october-2014/))

### Which TSOP chip do I have and what size?
- open Xbox and look at the chip for the name (Hynix, Hyundai, ST, Winbond, Sharp) ![alt text](https://i.imgur.com/hVNT8P2.png)
- Hynix, Hyundai, ST Chip uses the same flashing method
- Winbond uses different flashing method
- Sharp uses different flashing/soldering method
- Look at the power cable
  - **single row** is **1MB TSOP**, either Xbox **1.0 or 1.1** ![alt text](https://i.imgur.com/lS13LJI.png)
  - **double row** is **256KB TSOP**, from Xbox **1.2 thru 1.6** (1.6 does not have TSOP) ![alt text](https://i.imgur.com/wwmKWwD.png)

### Where to Solder for TSOP?
- For 1MB TSOP Motherboard
  - Front ![alt text](https://i.imgur.com/PDFrOVA.png)
  - Back ![alt text](https://i.imgur.com/mGAQtaA.png)
- For 256KB TSOP Motherboard
  - Front 1 ![alt text](https://i.imgur.com/RYqv1qi.png)
  - Front 2 ![alt text](https://i.imgur.com/j0G3BWz.png)
- For Sharp TSOP Motherboard Only ![alt text](https://i.imgur.com/UeSxFtG.png)
  - requires a few wires

### Flash the TSOP Chip
*Warning: Make sure the power does not go out else it will be bricked while flashing TSOP*

- Put in Hexen Boot Disc into Xbox DVD Drive
- Choose Your Chip BIOS:
- (**WARNING: Make sure the BIOS size is less or equal to the chip size**)
  - For Hynix, Hyundai, ST Only
    - Hexen > 3. TSOP Flash/Chipped Xbox Tools > 3.2 Modchip/TSOP Flash (Not Winbond) > Yes > Will load Evolution X > [Pick your BIOS to Flash]
      - For **256KB TSOP**: Evolution X > Flash 256k BIOS, 1.0-1.5 > **iND-BIOS.5003.67 F and G**
      - For **1MB TSOP**: Evolution X > Flash 512k BIOS, 1.0-1.5 > **X2.5035 F and G**
  - For Winbond Only (**256k BIOS**)
    - Hexen > 3. TSOP Flash/Chipped Xbox Tools > 3.3 Winbond or Sharp > **3.3.1 Flash iND-BIOS.5003.67 (F and G)**
  - For Sharp Only
    - Hexen > 3. TSOP Flash/Chipped Xbox Tools > 3.3 Winbond or Sharp > **Sharp Only Only Use On A Sharp TSOP**
- **>>Time to remove the Softmod Now That the Xbox is TSOP<<**
- After Flashing is done it will reboot. The xbox loading screen will be different if it worked. Make sure it reboot back into the Hexen Boot Disc
- Hexen > 3. TSOP Flash/Chipped Xbox Tools > 3.5 Chipped/Flashed Xbox Disk Upgrades > 3.5.2 Clean C partition after TSOP flash
  - **Passcode**: A Y B X START > Yes
- Hexen > 3. TSOP Flash/Chipped Xbox Tools > 3.6 Disk Lock/Unlock And eeprom Backup > Yes > Will load Evolution X
  - Evolution X > Backup eeprom
  - Evolution X > Unlock Disk > Yes
- Exit everything, reboot and remove Hexen Boot Disc. Your Done Son!


# TSOP Modded Hard Drive Upgrade
*Note: this is for TSOP modded xbox only aka model 1.0-1.5 not 1.6*
- Requirements:
  - New IDE Hard Drive
  - Working Xbox DVD Drive
  - Hexen Boot Disc
- Open xbox and replace Hard Drive
- **Make sure the jumper settings is the same on the newer HDD**
- Start the Xbox, it should give error message
- Insert Hexen Boot Disc > Power Off > Power On > This will reboot into Blue Screen
- UnleashX Blue Screen > Press Both Triggers and Start Button > It Will Format the new HDD
  - Do You have Drive F:\? **Over 100GB HDD then yes to Drive F, under 100GB then skip**
  - Wait for it to finish formatting the HDD
- Hexen > 5. Dashboard Tools > 5.2 Dashboard Repair Tools > 5.2.2 Install Dashboards > Yes
- Hexen > 7. Clean Up Installation Files
- Hexen > 9. Clear Cache
- Eject Disk and Reboot

### references
- http://xboxdrives.x-pec.com/?p=list
- http://vault-tec.info/post/90476753721/original-xbox-tricks
- http://xbmcxbox.blogspot.com/p/dashboard-5960.html
- http://cirreus.com/ar/xbox.html
- http://www.biline.ca/xbox_uxe_method2.htm
- EFFEKT Softmod https://www.youtube.com/watch?v=iHV6Vd3RGQo
- Ben Softmod https://www.youtube.com/watch?v=XlF8UDedjYc
- Xbox Cleanup https://www.youtube.com/watch?v=iSsXOlOUTgI
- TSOP Mod 1 https://www.youtube.com/watch?v=jg4ODhIblcg
- TSOP Mod 2 https://www.youtube.com/watch?v=GjgIuvQWrgM
- TSOP Upgrade HDD https://www.youtube.com/watch?v=v5zFiIXNhlY
- Clock Capacitor 1.4 location http://www.neogaf.com/forum/showthread.php?t=857527&page=4
- Emulator List http://xbmcxbox.blogspot.com/2013/03/complete-list-of-emulators-for-original.html


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


