# Xbox 360 Modchip Install

### What is JTAG/RGH?
A JTAG/RGH exploited console is modified to enable the running unsigned code. Both of these modification methods achieve the same thing, just in different ways, and they both have different requirements.

The JTAG modification is a software hack based upon an exploitable SMC which is why it can only be done to Kernals 7371 or lower and was patched in the 8XXXX+ kernals.

The RGH modification is a time based attack on the CPU that glitches the chip, and allows a moment for the exploit to take place and unsigned code to be run.

### Looking For Missing PowerBrick
  - PowerBrick and Console Motherboard ![alt text](https://i.imgur.com/yNU1sXV.png)


### What Xbox 360 Model Do I Have?
  - PHAT and SLIM ![alt text](https://i.imgur.com/Ffdj5OD.jpg)


### How To Check My Xbox 360 Dashboard Version?
- Xbox 360 > Settings > System > Console Settings > System Info

### Which Mod Chip Install Do I Use? ![alt text](https://i.imgur.com/ZaZ5CJP.png)


### How To Take Apart The Xbox 360?
- Phat Model: https://www.youtube.com/watch?v=5XCT1SqFlFg
- Slim Model: 
  - Take apart Slim Model (Glossy Trinity): https://www.youtube.com/watch?v=NOcjZA3Y3v8
  - Take apart Slim Model Front Plate (Glossy Trinity): https://www.youtube.com/watch?v=vjZYvM_Zhtk


### No Sound on HDMI Cable Fix
- Source: https://www.youtube.com/watch?v=NLwYcVhPuX8
- Xbox 360 > Settings > System > Console Settings > Display > Display Discovery > Disable
- Xbox 360 > Settings > System > Console Settings > Display > HDTV Settings > 1080p
- Xbox 360 > Settings > System > Console Settings > Audio > Digital Output
- Xbox 360 > Settings > System > Console Settings > Audio > Sound Effects > Enable Sound Effects

### Replace Thermal Paste
- Requirements:
  - Goo-Gone
  - Rubbing Alcohol
  - Q-tips
  - Scooper: Use old Giftcards
  - XClamp Removal Tool
  - Arctic Silver 5

### Reflash JR-Programmer V2 Firmware
- Source: https://www.youtube.com/watch?v=WXsD7yB7-Os
- Set to BL Mode: JR Programmer V2 > __Switch To The Right (Green) {BL MODE}__
  - Note: The switch near the reset button
- Connect JR Programmer V2 > USB > PC
- PC > J-Runner (run as admin) > Tools > Update JR-P fw > [jrunner/common/**PICFLASH_E_1_0_5-JRP-V2.HEX**]
  - Note: once its done, you will see the JR Programmer Logo in JRunner, and the light will be green

### Reflash Original Stock Nand
- Connect JR Programmer V2 > USB > PC
- PC > J-Runner (run as admin) > Load Source > [your_stock_nand.bin]
- PC > J-Runner (run as admin) >  __[Retail]__
- PC > J-Runner (run as admin) >  Build XeBuild
- PC > J-Runner (run as admin) >  __[Retail]__
  - Note: if J-Runner switches to something else make sure is back on Retail
- PC > J-Runner (run as admin) > Write Nand


## RGH 1.2 Jasper and Falcon PHAT Xbox 360

### Buy list
- Coolrunner Rev C or Matrix Glitcher V1
- JR Programmer or Nand-X
- Soldering Iron
- Flux
- 40 Pin 1x40 Single Row Male 2.54mm Breakable Pin Header

### Download Software
- JR-Programmer V2 Drivers: http://www.weekendmodder.com/JRPv2_drivers.zip
  - https://store.weekendmodder.com/index.php?route=product/product&path=60&product_id=214
- J-Runner with Extras https://mega.nz/#!AAEwSLRS!au6qMJbY-CsMTl92XjRQbhshkniheMwG4RIDZbZ2mAw

### RGH 1.2 Any PHAT Xbox 360
- **RGH1.2 PHAT Step 1**: Install the Modchip (Coolrunner RevC)
  - Wire Routing (Back) ![alt text](https://i.imgur.com/cgue5fp.jpg)
  - Wire Routing (Front): (Alternative GND Joint to side of Case) ![alt text](https://i.imgur.com/wpL5eeF.jpg)
  - Front & Back Joints CR RevC ![alt text](https://i.imgur.com/C5G5gtw.jpg)
  - Back Solder Joint: CLK Easy Alernative (Orange Wire on Mine) ![alt text](https://i.imgur.com/ohVLe05.png)
  - Back Solder Joint: POST ![alt text](https://i.imgur.com/0lHcCdg.png)
  - Back Solder Joint: PLL & RST ![alt text](https://i.imgur.com/KxOn43n.png)
- **RGH1.2 PHAT Step 2**: Solder Nand Header To Motherboard
  - Nand-X or JR Programmer V2 ![alt text](https://i.imgur.com/SBzV9Db.png)
- **RGH1.2 PHAT Step 3**: Program the Modchip (Timing Files for Coolrunner RevC)
  - CoolRunner RevC (**Switch to PHAT and NOR** on the chip) ![alt text](https://i.imgur.com/PMGJBfd.jpg)
  - Set to Programming Mode: JR Programmer V2 > __Switch To The Right (Blue) {CHIP MODE}__
  - Connect Coolrunner RevC > JR Programmer V2 > USB > PC
  - PC > J-Runner (run as admin) > Advanced > Custom Nand/CR Functions > [Xsvf] > Filename  ... > [rgh12_21.xsvf] > RUN (2 times to be sure)
    - **REMINDER: rgh12_21.xsvf is for RGH 1.2 PHAT Jasper/Falcon using CoolRunner RevC/Matrix Glitcher v1**
  - DONE! Disconnect Modchip and Programmer
- **RGH1.2 PHAT Step 4**: Read Two NAND Dumps, Create and Write ECC
  - Connect Xbox 360 Standby Power to the Xbox 360 __(DO NOT POWER ON)__
  - Set to Read & Write Mode: JR Programmer V2 > __Switch To The Left (RED) {NAND MODE}__ ![alt text](https://i.imgur.com/e8zFzvq.jpg)
  - Connect NAND Header Wire > JR Programmer V2 > USB > PC
  - PC > J-Runner v0.3 Beta8 (Run As Admin) > Motherboard > **?** ![alt text](https://i.imgur.com/yaoTsFS.jpg)
    - This will check which motherboard your console has
    - If You Get Flash Config 0x0000000 Then Double Check The Standby Power & Jr Programmer Switch In Correct Place
  - PC > J-Runner v0.3 Beta8 > Reads > **[2]**
  - PC > J-Runner v0.3 Beta8 > **Read Nand** > Type > OK
    - Each Nand Dumps should take about 5-15mins each, so 10-30mins total on the JR Programmer V2
    - Common To See "Error: 250 Reading Block AA0", Any Where Between 10-15 Error Blocks, Just Make Sure They Are The Same On Both Dumps
    - Common To See "Bad Blocks Remap"
    - When It Finish It Should Say: __NANDS ARE THE SAME__
  - __Backup The Nand Dumps Files (nanddump1.bin nanddump2.bin checksum.md5) Somewhere Safe__
  - PC > J-Runner v0.3 Beta8 (Run As Admin) > __[Glitch2]__ > **Create ECC** > Type > OK
    - Note: J-Runner > Load > Source; should now say: **image_00000000.ecc**
  - PC > J-Runner v0.3 Beta8 (Run As Admin) > __[Glitch2]__ > **Write ECC** > Type > OK
    - Note: This will write Xell to the Xbox 360
  - DONE! Disconnect Programmer
- **RGH1.2 PHAT Step 5**: Get CPU Key
  - Disconnect any Programmer
  - Connect:
    - Fans
    - Fan Cover
    - Ethernet Cable
    - HDMI
    - Power Cord
    - Ring of Light Board
  - Bootup the Xbox 360 > Wait for Xell Reloaded to Complete its startup process ![alt text](https://i.imgur.com/KvF3lMF.png)
    - Note: Xell > Network Config > 192.168.1.XXX ; easy way to get cpu key using this ip
  - PC > J-Runner v0.3 Beta8 (Run As Admin) > IP > [192.168.1.XXX] > Get CPU Key
    - Note: Now we have more info: J-Runner > KV Info
  - DONE! Power off the Xbox 360
- **RGH1.2 PHAT Step 6**: Install XeBuild & Write Nand
  - Unplug Ethernet
  - Connect Xbox 360 Standby Power to the Xbox 360 __(DO NOT POWER ON)__
  - Set to Read & Write Mode: JR Programmer V2 > __Switch To The Left (RED)__
  - Connect NAND Header Wire > JR Programmer V2 > USB > PC
  - PC > J-Runner v0.3 Beta8 (Run As Admin) > __[Glitch2]__ > **Create XeBuild Image**
    - Note: Warning > smc.bin found. Delete it? Unless you put it there, delete it! > YES
    - Note2: it should generate a new file once finish; J-Runner > Load Source > **updflash.bin**
  - PC > J-Runner v0.3 Beta8 (Run As Admin) > __[Glitch2]__ > **Write Nand** > Type > OK
    - Note: Take about 15mins to finish
  - __Backup Nand Dumps Files, ECC, CPU Key, UpdFlash...etc Somewhere Safe__
- **RGH1.2 PHAT Step 7**: Test Run
  - Bootup the Xbox 360 console a few times to see how fast it boots
    - Note: Re-program the modchip with a different timing file if you like to see different results
- **RGH1.2 PHAT Step 8**: Clean Up
  - DeSolider The Nand Header Wires
  - Rubbing Alcohol and Q-Tips Clean All Solder Joints
  - Put the Xbox 360 console back together
  - DONE SON!

### Reset Family Code
- Source: https://www.se7ensins.com/forums/threads/unlocking-parental-block-tutorial-factory-reset.1296238/
- Requirements:
  - Nanddump.bin of your Xbox 360
  - J-Runner
- PC > J-Runner (run as Admin) > Load Source > [nanddump.bin]
- PC > J-Runner (run as Admin) > Tools > SMC Config Editor > *Your Reset Code*
- Xbox 360 > Settings > System > Console Settings > System Info > Press Combo: LT, RT, X, Y, LB, RB, [Your Reset Code]

### 001 Install XexMenu 
- Source: https://www.youtube.com/watch?v=eq-ky8T6kl4
- Info: File Manager
- Requirements:
  - USB Flash Drive
  - PC
  - Download XexMenu 1.2
    - https://mega.nz/#!9AlUmDZK!oykniipcx80kvuRxLaqY8NtPMJYKHW1ZYpqYfcAZsLA
- Format USB Drive from Xbox 360
  - Plug USB Flash Drive Into the Xbox 360
  - Xbox 360 > Settings > System > Storage > USB Storage Device > Press Y > Format > Yes
  - Remove Flash Drive from the Xbox 360 and Plug into the PC
- PC > Extract XexMenu 1.2
  - Output: 0000000000000000/C0DE9999/00080000/C0DE99990F586558
  - Note: create the zero folder if it doesnt exist
- cp 0000000000000000/C0DE9999/00080000/C0DE99990F586558 USB:/Content/
- Eject USB Drive And Plug Into Xbox 360
- Make sure Ethernet / Wireless is not connected on the Xbox 360
- Xbox 360 > Settings > System > Storage > USB Storage Device > Press A > Demos > XeXMenu 1.2 > Press A > Copy > Hard Drive
  - Note: if it says currupted than you do not have a modded xbox 360
- Xbox 360 > Games > My Games > XeXMenu 1.2
- XeXMenu hotkeys:
  - RB = Top Drive
  - X  = Change Drive
  - B  = Go Back
  - Y  = Copy, Cut, Paste, Delete, Create

### 002 Install Dashlaunch
- Source: https://www.youtube.com/watch?v=y2zCQD0RaeA
- Info: Plugins, Mod Tools, Change Paths, Autostart Program, LiveBlock
- Requirements:
  - USB Flash Drive FAT32
  - PC
  - Download Dashlaunch 3.18.1
    - https://digiex.net/threads/dash-launch-3-18-1-for-jtag-rgh-xbox-360s-running-freeboot.11024/
- extract Dashlaunch_3.18.1.zip
- cp Dashlaunch_3.18.1/ USB:/Dashlaunch_3.18.1
- eject USB > plug into xbox 360 > start xbox 360
- Make sure Ethernet / Wireless is not connected on the Xbox 360
- Xbox 360 > Games > My Games > XeXMenu 1.2
- XeXMenu > Press X > HDD1: > Highlight Content > Press Y > Create > Name it (Homebrew)
- XeXMenu > Press X > USB0: > Highlight Dashlaunch_3.18.1 > Press Y > Copy (Press A)
- XeXMenu > Press X > HDD1: > Homebrew > Press Y > Paste (Press A)
- XeXMenu > Press X > HDD1: > Homebrew > Dashlaunch_3.18.1 > Installer > default.xex > Press A
  - Note: if it ask to update then update it
- Dashlaunch > Behavior > contpatch > enabled
  - Note: addon and DLC content license info will be soft patched when accessed
- Dashlaunch > Network > pingpatch > enabled
  - Note: ping limit will be removed for system link play
- Dashlaunch > Network > liveblock > enabled
  - Note: blocks MS DNS to avoid ban on modden console
- Dashlaunch > Configurator > ftpserv > enabled
- Dashlaunch > Press RB > HDD > Press X > Press A (Turns Green) > Press X
  - Note: this will save settings to the HDD instead of the USB flash drive
- Dashlaunch > Press RB > System Info > CPU Fan Speed Override > [60 or 65] > Press A to save
- Dashlaunch > Press B a few time to exit

### 003 Install Aurora ( Custom Dashboard ) & Make Aurora the Default Dashboard
- Source: https://www.youtube.com/watch?v=Kqvruf8q3J0
- Info: Plugins, Mod Tools, Change Paths, Autostart Program, LiveBlock
- Requirements:
  - USB Flash Drive FAT32
  - PC
  - Download Aurora 0.6b
    - http://phoenix.xboxunity.net/downloads/Aurora%200.6b%20-%20Release%20Package.rar
    - http://phoenix.xboxunity.net/#/news
- extract Aurora_0.6b.rar
- cp Aurora_0.6b/ USB:/Aurora_0.6b/
- eject USB > plug into xbox 360 > start xbox 360
- Create an account to play online for free: PC > Web Browser > http://xboxunity.net > Register > Activate via Email
- Reboot Xbox 360 if you just installed Dashlaunch
- Connect Ethernet or Wireless Adapter to the Xbox 360
- Enable Internet: Xbox 360 > Settings > System > Network Settings > Wired
- Xbox 360 > Games > My Games > XeXMenu 1.2
- XeXMenu > Press X > USB0: > Highlight Aurora_0.6b > Press Y > Copy (Press A)
- XeXMenu > Press X > HDD1: > Homebrew > Press Y > Paste (Press A)
- XeXMenu > Press X > HDD1: > Homebrew > Aurora_0.6b > Aurora.xex > Press A
- Confirm IP Address: Aurora > Press Back
- Aurora > Press Start > Unity > Enable > Username > [Your Username] > API Key > Request > [Your Password]
- Autostart Aurora Dashboard:
  - Aurora > Press Start > Content > Manage Paths > Add > Path > Change > HDD1 > Highlight Homebrew > Press Y
  - Aurora > Press Start > Content > Manage Paths > Add > Depth > [2]
  - Aurora > Press Start > Content > Manage Paths > Add > Script Data > [Homebrew] > Save
- Dashlaunch > Paths >  Default > HDD > Homebrew > Aurora > Aurora.xex > Press X > Press RB > HDD > Press X to save
  - Note: Press LB to go back to Dashlaunch Main Menu
- Dashlaunch > Paths > BUT_X > HDD > Content > 0000000000000000/C0DE9999/00080000/XeXMenu 1.2 > Press X > Press RB > HDD > Press X to save
- DONE! Aurora Is Now The DEFAULT Dashboard:
  - Launch Aurora Dashboard: Press Guide > Press Y > Yes
  - Launch Official Xbox 360 Dashboard: Press Guide > Press Y > Yes > HOLD Down RB Button
  - Launch XeXMenu: Press Guide > Press Y > Yes > HOLD Down X Button

### 004a Install Games via USB
- Source: https://www.youtube.com/watch?v=wCs8bIwifzk
- Download Games
- Extract game ISO Image using extract-xiso
- Copy to USB Drive
- Xbox 360 > Games > My Games > XeXMenu 1.2
- Create New Folder: XeXMenu > Press X > HDD1: > Press Y > Create (Press A) > Games
- XeXMenu > Press X > USB0: > Highlight NBA_Street_V3 > Press Y > Copy (Press A)
- XeXMenu > Press X > HDD1: > Games > Press Y > Paste (Press A)
- Refresh Aurora To List The New Games:
  - Aurora Dashboard: Press Guide > Press Y > Yes
  - Note: Make Sure You Are Connect To The Internet
  - Aurora > Press Start > Content > Manage Paths > Add > Path > Change > HDD1 > Highlight Games > Press Y
  - Aurora > Press Start > Content > Manage Paths > Add > Depth > [2]
  - Aurora > Press Start > Content > Manage Paths > Add > Script Data > [Applications] > Save

### 004b Get Games Updates and Install
- Source: https://www.youtube.com/watch?v=wCs8bIwifzk
- Get Game Updates
  - Aurora > Highlight NBA_Street_V3 > Press Y > Title Updates (Controller Icon) > Press A > Press RB (Unity Marketplace Tab) > [Pick Version] > Press A > Wait For It To Finish Downloading > Press LB (Installed Tab) > Enable (Press A)
  - Aurora > Highlight NBA_Street_V3 > Press Y > Launch (Play Icon) > This Will Apply The New Updates and Start The Game

### 004c Transfer Games via FTP
- Source: https://www.youtube.com/watch?v=wCs8bIwifzk
- Enable FTP
  - Aurora > Press Start > Modules > FTP Server > Module > [Enabled]
  - Aurora > Press Start > Modules > FTP Server > Port > [21]
  - Aurora > Press Start > Modules > FTP Server > Username > [xbox]
  - Aurora > Press Start > Modules > FTP Server > Password > [xbox]
- PC > Filezilla > Connect To The Xbox360 > Transfer The Games To HDD1:/Games/

### 005a Install DLC
- Source: https://www.youtube.com/watch?v=i2xZ8ZIt0wE
- Make Sure You Have The Newest Updates. Follow Steps '004b Get Games Updates and Install'
- Lanuch The Game Once: 
  - Aurora > Highlight NBA_Street_V3 > Press Y > Launch (Play Icon) > It Will Start the Game and Create Folder Structure
  - Aurora Dashboard: Press Guide > Press Y > Yes
- PC > Web Browser > http://www.xbox360iso.com/forumdisplay.php?126-JTAG-RGH-Downloadable-Content&s=92173bca6d2c3f91e3697c4c528ffb7b
  - look for the game DLC you want to download
  - extract DLC to USB Drive
    - USB:/[GameID]/[DLC_Folder]/[DLC_Files]
    - USB:/415608C3/00000002/4353480842303294230
    - USB:/415608C3/00000002/F93454JKS9023943204
    - USB:/415608C3/00000002/8043934389912HJSD55
- Plug in USB to Xbox360
- XeXMenu: Press Guide > Press Y > Yes > HOLD Down X Button
- XeXMenu > Press X > USB0: > [GameID] > Highlight [DLC_Folder] > Press Y > Copy (Press A)
- XeXMenu > Press X > HDD1: > Content > [GameID] > Press Y > Paste (Press A)

### 005b Install XM360
- Download XM360v2 https://digiex.net/threads/xm360-2-0d-download-xbox-360-jtag-xbla-dlc-tu-content-organiser.7999/
  - Info: XM360 lets you see your content, and manage it, content that it is aware of is: XBLA, DLC, Title Updates, and Game Saves.
  - Note: This program is use to unlock the DLC, however most times the DLC you download is already unlocked. So you can skip it
- Extract XM360v2 to USB:/XM360/
- Plug in USB to Xbox360
- XeXMenu > Press X > USB0: > Highlight XM360 > Press Y > Copy (Press A)
- XeXMenu > Press X > HDD1: > Homebrew > Press Y > Paste (Press A)
- Aurora Dashboard: Press Guide > Press Y > Yes
- Aurora > XM360 > Take a while to load (Black Screen)
- XM360 > Scan All
- XM360 > Show DLC
- XM360 > Unlock DLC > (The Lock Icon will turn into Unlock Icon)
  - Note: somewill already be unlocked by contpatch from dashlaunch settings, regardless of the locked icon
- XM360 > Exit to Dash
- Start Your Game and DLC should be working with it


- Dashlaunch > Behavior > contpatch > enabled
  - Note: addon and DLC content license info will be soft patched when accessed
- Dashlaunch > Press RB > HDD > Press X > Press A (Turns Green) > Press X
  - Note: this will save settings to the HDD instead of the USB flash drive
- Dashlaunch > Press B a few time to exit

### 006a Copy Game Disc to Hard Drive (via Aurora)
- Source: https://www.youtube.com/watch?v=wWTXja965gE
- Put in Disc to Xbox 360
- Aurora > Press Back > File Manager > DVD > Press X on each file & folder
- Aurora > Press Back > File Manager > DVD > Press Left > Copy (5th Icon Down) > Press A
- Aurora > Press Back > File Manager > DVD > Press Left > Copy (5th Icon Down) > Press A
  - Note: Press B a few times to go back
- Aurora > Press Back > File Manager > HDD1 > Games > MYRIPPEDGAME > Paste (6th Icon Down) > Press A > YES
  - Note: It will now rip the DVD to HDD
- TEST THE GAME: Aurora > Press Back > File Browser > HDD1 > Games > MYRIPPEDGAME > default.xex

### 006b Copy Game Disc to Hard Drive (via XeXMenu Method 1)
- Launch XeXMenu: Press Guide > Press Y > Yes > HOLD Down X Button
- XeXMenu > Press X > HDD1: > Games > Press Y > Create > MYRIPPEDGAME_V2
- XeXMenu > Press X > DVD: > Highlight A File > Press Y > Copy (Press A)
- XeXMenu > Press X > HDD1: > Games > MYRIPPEDGAME_V2 > Press Y > Paste (Press A)
  - Note: Repeat copying every single file from the DVD to the MYRIPPEDGAME_V2

### 006c Copy Game Disc to Hard Drive (via XeXMenu Method 2)
- Launch XeXMenu: Press Guide > Press Y > Yes > HOLD Down X Button
- XeXMenu > Press X > HDD1: > Games > Press Y > Create > MYRIPPEDGAME_V3
- XeXMenu > Press X > HDD1: > Games > MYRIPPEDGAME_V3 > Press Y > CopyDVD (Scroll Down to the Bottom) > Press A > It will Eject Disc > Put Game In and Close Tray > Confirm

### 006d Copy Game Disc to Hard Drive (via Xbox 360 Neighborhood)
- Connect to the Xbox 360
- Copy DVD content and Paste to Xbox 360 Hard Drive

### 007 Installing Xbox 360 Neighborhood
- Source: https://www.youtube.com/watch?v=aqmO-T7LlTc
- PC > Install XBOX360_SDK_21256.3.exe
  - http://www.mediafire.com/file/l9786i9endh5w5e/XBOX360+SDK+21256.3.exe
- PC > Download xbdm.xex
  - https://www.sendspace.com/file/qns1vg
- PC > copy xbdm.xex to USB Drive
- Launch XeXMenu: Press Guide > Press Y > Yes > HOLD Down X Button
- XeXMenu > Press X > USB0: > Highlight xbdm.xex > Press Y > Copy (Press A)
- XeXMenu > Press X > HDD1: > Press Y > Paste (Press A)
- Dashlaunch > Plugins > plugin1 > HDD > xbdm.xex > Press RB > highlight HDD > Press X to save
  - Note: Press B a few times to exit
- RESTART THE XBOX 360 CONSOLE
- Aurora > Press Back > copy down Xbox360 IP Address
- PC > Xbox 360 Neighborhood > Next > [Xbox360 IP Address] > Next > Yes > DONE!
  - Note: You can now access it remotely like a samba share

### 008a Updating The Dashboard (17511)
- Source: https://www.youtube.com/watch?v=iKpcO4jhU24
- CHECK VERSION: Xbox 360 > Settings > System > Console Settings > System Info
- Download XeBuild GUI (17511)
  - https://xbls.ninja/NAND
- Download Simple 360 Nand Flasher
  - http://www.homebrew-connection.org/simple-360-nand-flasher-v1-2-by-swizzy-corona-4gb-nand-dump-and-write-support-added/
- Copy to Xbox 360
  - XBOX360 > HDD1 > Homebrew > Simple 360 Nand Flasher
- Simple 360 Nand Flasher > Press X > It will Start reading the firmware > Press A to exit
  - Note: it will output a file called **flashdmp.bin**
- Copy to PC
  - XBOX360 > HDD1 > Homebrew > Simple 360 Nand Flasher > flashdmp.bin > Copy to PC
- PC > xeBuild_GUI_2.0.exe > Source File > Open > [flashdmp.bin]
- Turn off XBOX360
- START XELL: Press Eject Button on the XBOX360 Console
- PC > xeBuild_GUI_2.0.exe > IP to Xell > [IP Address] > Get CPUKey/CFLDV from Network
- REBOOT XBOX360
- PC > xeBuild_GUI_2.0.exe > Kernel version > [2.0.17511.0]
  - Note: everything should be checked at the bottom now: Type, source, output, motherboard, cpukey ...etc
- PC > xeBuild_GUI_2.0.exe > Special Patches > [x] Disable FCRT ban check
  - Note: This is for slim models only
- PC > xeBuild_GUI_2.0.exe > Check KV
- PC > xeBuild_GUI_2.0.exe > Generate hacked image > No
  - Note: this will output a file called **updflash.bin**
- Copy updflash.bin to XBOX360 > HDD1 > Homebrew > Simple 360 Nand Flasher
- Simple 360 Nand Flasher > Press A (Flash your Nand) > Once done it will shutdown
- CHECK VERSION: Xbox 360 > Settings > System > Console Settings > System Info
 
### 008b Avatar Assets Update (17511)
- Source: https://www.youtube.com/watch?v=iKpcO4jhU24
- Make sure you have the latest dashboard installed before doing this update, else it will BRICK
- Xbox Update Download for Avatar Assets
  - Go to https://support.xbox.com/en-GB/xbox-360/console/system-updates-info > click Copy to a USB Flash Drive > 2. Download the update file
- Extract SystemUpdate_17511_USB.zip to USB:/$SystemUpdate
- Rename to USB:/$$ystemUpdate
- Plug USB stick into Xbox360 > Update Required > Yes
  - Note: once is done you should see your avatar character now

### 009 How To Play On Xbox Live With A Modded Xbox 360 (Stealth Server)
- Source: https://www.youtube.com/watch?v=KWWsWr7XUJ0


### 010 Installing Call of Duty Mod Menu
- Source: https://www.youtube.com/watch?v=RHLCcItneWQ

### 011 How to use RTE Mod Tools
- Source: https://www.youtube.com/watch?v=Q1BqiNqYxeg

### 012 Play Original Xbox on RGH Xbox 360
- Source: https://www.youtube.com/watch?v=uO9wbrux_xE
- List of Original Xbox games that works https://support.xbox.com/en-US/legacy-devices/original-console/play-original-games
- extract-xiso GTA.iso
- mkdir USB:/Xbox1
- cp GTA/ to USB:/Xbox1/GTA/
- Download hdd_compat_partition_fixer_v1.zip
  - http://ep-comps.com/free60/?dir=/XBox%201%20Compatability
- Extract and put into USB:/Homebrew/hdd_compat_partition_fixer_v1
- XeXMenu > copy USB:/Homebrew/hdd_compat_partition_fixer_v1 to Xbox360:/HDD1/Homebrew/
- XeXMenu > HDD1/Homebrew/hdd_compat_partition_fixer_v1/default.xex
- hdd_compat_partition_fixer_v1 > Press A (Write Compat partition to HDD) > Wait for it to finish > Press B to exit > Manually Restart XBOX
  - Note: this will format partition 2 aka **HDDX**
- Start Xbox360 > XeXMenu > HDDX should now be empty
- PC > Download and extract xb1_5829_nov_2007-hacked.zip
- Copy Compatibility folder to XBOX360:/HDDX/Compatibility
- Now Start any Original Xbox Games

## RGH: CR4 Muffin Trinity Xbox 360 Slim (via CR_RevC)
- Source: https://www.youtube.com/watch?v=5Liw1TtwoOU
- Sync with Controller 1st before starting
- CoolRunner Rev C
  - Remove JP
  - Remove C8
- CoolRunner Rev C Timing Files
  - Use muffin_7-1_dt.xsvf
    - https://mega.nz/#!FAkUjCLb!rbFH_zlhdZJrlBpxfzsv9dbPbXskg1d2PNFBCrLmNOA
- Slim Trinity Only
  - F        = N/A
  - E        = DB2G3 (Front) or FT2V1 (Back) - purple wire cut #2
  - D (RST)  = FT4R2 (Back) - {other side of scatter plot} - orange wire
  - C (POST) = FT5R17 (Back) - {scatter plot} - yellow wire
  - B (CLK)  = FT3N2 (Back) - purple wire cut #1
  - A        = N/A
  - GND      = Ground to Case or J2C3 - black wire
  - 3v3      = Power to J2C3 - red wire
- ![alt text](https://i.imgur.com/BTW1dFg.jpg)


### Emulators
Current emulator versions:
FCE360-V0.6
mame_0.72_Release2
Snes360_v0.32_Beta
Genesis-Plus-360-0.18-Beta-Version-XEX

Directory for Hdd:
Snes = hdd:\Emus\Snes360\roms
GenesisPlus = hdd:\Emus\genesis360\roms
Mame = hdd:\Emus\mame\roms   (Make sure you change the option file like I show you in Part 2)

Directory for USB Storage Device:
Snes = usb:\_Emus\Snes360\roms (You MUST have the _)
GenesisPlus = usb:\_Emus\genesis360\roms   (You MUST have the _)
Mame = USB:\Emus\mame\roms   (Make sure you change the option file like I show you in Part 2)


### FTP Speed Up
- Source: https://www.xbmc4xbox.org.uk/forum/viewtopic.php?t=1012
- PC > Filezilla > Edit > Settings > Transfers> Maximum simultaneous transfers: [9]
- PC > Filezilla > Edit > Settings > Transfers> File Types > Default transfer type: [Binary]
- PC > Filezilla > Server > Force showing hidden files [X]
- OGXbox > UnleashX > Xbox Admin > System > Settings > Network>Set Max No Of Users to [10]
- OGXbox > Reboot

### references
- ReFlash JR Programmer V2 Firmware: https://www.youtube.com/watch?v=WXsD7yB7-Os
- List of Compatability for Original Xbox games https://support.xbox.com/en-US/legacy-devices/original-console/play-original-games
- 2017 Updated JTAG RGH Tutorials by xxModdedWarfarexx https://www.youtube.com/playlist?list=PLn7ji3VsPy3FCoZ5E3zWz5tS5iWbysPZX
- 2013 The JTAG Tutorial Series by xxModdedWarfarexx https://www.youtube.com/playlist?list=PLn7ji3VsPy3G08cHNCHyT4Yj-WWYhw8D7
- Xbox DVD tray stuck manual eject https://www.youtube.com/watch?v=QV-1RF5MIwk
- Xbox DVD tray stuck clean rubber band https://www.youtube.com/watch?v=qWXBDGPL8GE
- Take apart Phat Model: https://www.youtube.com/watch?v=5XCT1SqFlFg
- Take apart Slim Model (Glossy Trinity): https://www.youtube.com/watch?v=NOcjZA3Y3v8
- Take apart Slim Model Front Plate (Glossy Trinity): https://www.youtube.com/watch?v=vjZYvM_Zhtk
- Trinity CR4 Muffin Guide http://weekendmodder.com/TrinityRGH.html
- Trinity CR4 Muffin (Matrix Glitcher v1) https://www.youtube.com/watch?v=5Liw1TtwoOU
- Trinity CR4 Muffin Timing Files https://mega.nz/#!FAkUjCLb!rbFH_zlhdZJrlBpxfzsv9dbPbXskg1d2PNFBCrLmNOA
