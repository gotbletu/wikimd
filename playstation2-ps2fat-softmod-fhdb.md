# Playstation 2 SoftMod FHDB to IDE HDD (FAT PS2)
Softmod a FAT PS2 to play backup iso from an IDE Hard Drive. Basically we are going to format the hard drive and install FHDB software on it. **FHDB (Free HDBoot or Free Hard Drive Boot)** is an exploited software that allows you to run homebrew or play backup iso games. Think of it like booting a live linux cd and from there running any software we want.

* tutorial video: [Link](https://www.youtube.com/user/gotbletu)
* offical website: [Link](https://www.youtube.com/user/gotbletu)

### hardware requirements
- ps2 console (FAT version)
- ps2 network adapter
- computer with windows OS (software requires windows, linux wine doesnt seem to work)
- 3.5 inch IDE hard drive
- IDE to USB Adapter (to connect the HDD to the PC)
- flat head screwdriver

### software requirements
- Windows OS (XP/7/8/10...etc. I'm using Win7)
- WinHIIP 1.7.6 (Format HDD or Add/Remove Games)
  - http://www39.zippyshare.com/v/9mwrggPY/file.html
- FHDB1.93.img (image with Free HDBoot softmod preloaded)
  - http://psx-scene.com/forums/f153/unofficial-fhdb-1-93-noobie-package-obt-119562/
  - https://www.mediafire.com/?erxbqbgdajda0x4
- HDD Raw Copy (write image to hard drive)
  - http://www.hddguru.com/software/HDD-Raw-Copy-Tool/

### format hard drive
- right click and run WinHIIP.exe as administrator **Using Windows 7**
- WinHIIP > Select Drive > [Your_PS2_Hard_Drive]
- WinHIIP > Format Drive > Format > Application > Erase Mode > [Quick]
- WinHIIP > Format Drive > Format > Application > [HDLoader 28bit or HDLoader 48bit] (**Note: select 48bit for 120GB HDD or higher**)
- Close program when finish

### write FHDB (Free HDBoot) image to hard drive
- extract FHDB1.93.img.7z
- run HDDRawCopy.exe
- **Screen1: (Please Select SOURCE)**
- HDDRawCopy > FILE > Double Click to open file > [FHDB1.93.img]
- HDDRawCopy > Continue
- **Screen2: (Please Select TARGET)**
- HDDRawCopy > USB > [Your_PS2_Hard_Drive]
- HDDRawCopy > Continue
- HDDRawCopy > START
- Close program when finish

### add games
- connect HDD to PC
- right click and run WinHIIP.exe as administrator
- WinHIIP > Select Drive > [Your_PS2_Hard_Drive]
- WinHIIP > Add Images > Image Files > Add Images > [Your_PS2_GAMES] > OK
- Repeat to add more games

### test it out
- safely eject the USB ide hard drive from PC
- switch off the power for the hard drive power wire
- remove USB wire from PC
- connect HDD to the PS2 Network Adapter then to the PS2
- it should boot into Free HDBoot Menu if it works
- __Note: make sure the IDE HDD jumper is set to [Master] or [Cable Select] before inserting into the PS2__
- if it does not work it can either be the PS2 not detecting the hard drive, the hard drive is not compatible, the ps2 network adapter is not working or loose connection with the hard drive.

### play game
- PS2 > Free HDBoot > Open PS2 Loader > [Select_Your_Game]

# Format Hard Drive using PS2 Console and Free McBoot Memory Card
- Install HDD to PS2
- Boot PS2 into Free McBoot
- PS2 > Free McBoot > HD Loader > It will detect HDD and ask to Format

# Create PS2 FreeMcBoot (FMCB) Memory Card
*Info: Theres two methods but both requires that Free McBoot is already preinstalled some how.*

- Requirements:
  - PS2 Controller (official only, 3rd party brand might not work, PS1 controller wont work)
  - PS2 Memory Card (official only, a 3rd party brand might not work)
  - Flash Stick (aka USB Flash Drive)
  - Free McBoot 1.94 (FMCB1.94_NP.zip)
    - http://psx-scene.com/forums/f153/free-mcboot-1-94-noobie-package-125198/
- **>>>Method 1: Install FreeMcBoot (FMCB) to Memory Card from existing Free HDBoot (FHDB) PS2**
  - **Note: Requires a PS2 With Free HDBoot (FHDB) preinstalled already**
  - Format the Flash Stick to **FAT32**
  - Extract **FMCB1.94_NP.zip** and put it into Flash Stick
  - Plug in Memory Card into Slot 1 on PS2
  - Plug in Flash Stick into the PS2 USB port (any port)
  - Start PS2 wait until it boots into Free HDBoot Menu
  - Free HDBoot > **uLaunchELF HDD** > Press X > Press O for **File Browser** > **mass:/** > Press X > **FMCB1.94_NP/** > Press X > **FMCBInstaller.elf** > Press X > This will load FMCB install screen
    - FMCB > **Format MC** > Press O > Yes > Press O > OK > Press O
    - FMCB > **Multi Install** > Press O > Yes > Press O > wait until it finish installing > OK > Press O
    - FMCB > **Exit** > Press O
    - PS2 Memory Card Menu > Press O for Back
  - Power off the PS2
  - Finish, now you can use the memory card on **any FAT or Slim PS2 and it will run FreeMcBoot at startup**
- **>>>Method 2: Install FreeMcBoot (FMCB) to Memory Card from Another Free McBoot PS2 Memory Card**
  - **Note: Requires a PS2 Memory Card with Free McBoot (FMCB) preinstalled already**
  - Format the Flash Stick to **FAT32**
  - Extract **FMCB1.94_NP.zip** and put it into Flash Stick
  - Plug in the **Free McBoot Memory Card into Slot 1** on the PS2
  - Plug in Flash Stick into the PS2 USB port (any port)
  - Plug in the **second Memory Card into Slot 2** on the PS2
  - Start PS2 wait until it boots into Free McBoot Menu
  - Free McBoot > **uLaunchELF HDD** > Press O > Press O for **File Browser** > **mass:/** > Press O > **FMCB1.94_NP/** > Press O > **FMCBInstaller.elf** > Press O > This will load FMCB install screen
    - FMCB > **Format MC** > Press O > **Slot 2** > Press O > Yes > Press O > OK > Press O
    - FMCB > **Multi Install** > Press O > **Slot 2** > Press O > Yes > Press O > wait until it finish installing > OK > Press O
    - FMCB > **Exit** > Press O
    - PS2 Memory Card Menu > Press O for Back
  - Power off the PS2
  - Finish, now you can use the memory card on **any FAT or Slim PS2 and it will run FreeMcBoot at startup**

# Upgrade to OPL 0.9.3
- Requirements:
  - Free McBoot Memory Card
  - USB Flash Stick
- Format USB Flash Stick to **FAT32**
- Download OPL 0.9.3 and **extract it to USB Flash Stick**
  - OpenPS2Loader_0.9.3.zip https://bitbucket.org/ifcaro/open-ps2-loader/downloads/
- Start PS2 with **FreeMcBoot on Slot 1** and USB Stick plugged into the PS2
- PS2 > uLaunchELF > **mass:/OpenPS2Loader_0.9.3/OPL 0.9.3 (VMC+GSM+PS2RD)** > Press R1 > **Copy**
- PS2 > uLaunchELF > **mc0:/** > Press R1 > **Paste** > Wait for it to finish copying files over
- Restart PS2
- PS2 > Free McBoot Configurator > Press O (skip welcome) > Configure OSDSYS options > Configure Item > [Use Dpad Left or Right and **Find a blank item** like on Item 7] > **Press O**
  - Name: **OPL 0.9.3**
  - Path1: **mc0:/OPL 0.9.3 (VMC+GSM+PS2RD)/OPL 0.9.3 (VMC+GSM+PS2RD).ELF**
- Return > Return
- PS2 > Free McBoot Configurator > **Save CNF to MC0** > Press O
- Exit
- Press O to skip Memory Card Screen
- Now back on the Free McBoot Screen there should be a **OPL 0.9.3 in the menu**
- Finish!

# Play over ethernet port (Router Method)
*Info: the USB 1.1 on PS2 is very slow, ethernet is faster*
- Requirements:
  - Router with multiple ethernet ports
  - Ethernet Cables (1 to PC, 1 to PS2)
  - PS2 with FreeMcBoot or FreeHDBoot preinstalled
  - PS2 ISO games
  - Computer with Samba enable
  - OpenPS2Loader (OPL) 0.9.3 {anything lower wont work}

### On Linux
- Setup Samba Server
- Share a Folder and call it **ps2smb**


    sudo vim /etc/samba/smb.conf


    [global]
    # name you want to use
    server string = archlinux

    # windows workgroup name
    workgroup = WORKGROUP

    # name Windows Machines will see (max = 15 character)
    netbios name = archserver

    # only existing user can access samba
    #security = user
    #encrypt passwords = yes

    # set default guest account
    #guest account = nobody

    # a share that is accessible anonymously (guest access)
    map to guest = Bad User

    # for linux
    name resolve order = bcast host

    # load external conf
    # include = /etc/samba/smbshared.conf

    # Folder for my PS2 ISO Roms
    [ps2smb]
      path = "/media/EdoTensei/Romulan/sony playstation 2"
      browsable = yes
      guest ok = yes
      read only = yes
      available = yes
      writable = no

- Inside ps2smb create a **DVD** or **CD** folder
  - Example:
    - DVD size games smb://archserver/ps2smb/DVD
    - CD size games smb://archserver/ps2smb/CD
- How to find my ip address, mask, and gateway?


    # show ip/netmask
    # ip are usually (192.168.1.XXX)
    # mask are usually (255.255.255.0)
    $ ifconfig     # oldschool way to get ip
    
    # exmaple output:
    enp5s0: flags=4163<UP,BROADCAST,RUNNING,MULTICAST>  mtu 1500
            inet 192.168.1.100  netmask 255.255.255.0  broadcast 192.168.1.255
            inet6 ff80::8ae1:33c6:4b0b:7a05  prefixlen 64  scopeid 0x20<link>
            ether d4:3d:7e:f5:b9:a9  txqueuelen 1000  (Ethernet)
            RX packets 5457806  bytes 2117439885 (1.9 GiB)
            RX errors 0  dropped 0  overruns 0  frame 0
            TX packets 10806654  bytes 14599762295 (13.5 GiB)
            TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0

    -------------------------
    $ ip a         # new way to get ip on most distro
    
    # exmaple output:
    2: enp5s0: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc fq_codel state UP group default qlen 1000
        link/ether d4:3e:7e:e5:b9:a9 brd ff:ff:ff:ff:ff:ff
        inet 192.168.1.100/24 brd 192.168.1.255 scope global dynamic enp5s0
           valid_lft 80592sec preferred_lft 80592sec
        inet6 fe80::8ea1:33f6:4a0d:7c05/64 scope link
           valid_lft forever preferred_lft forever

    -------------------------
    # show the gateway address
    # gateway ip are usually (192.168.1.1) aka your router ip
    # in my case it says router.asus.com aka 192.168.1.1
    $ netstat -r
    
    # exmaple output:
    Kernel IP routing table
    Destination     Gateway         Genmask         Flags   MSS Window  irtt Iface
    default         router.asus.com 0.0.0.0         UG        0 0          0 enp5s0
    192.168.1.0     0.0.0.0         255.255.255.0   U         0 0          0 enp5s0
    
- So we gather all the ip information we need
- IP: inet **192.168.1.100**
- Mask: netmask **255.255.255.0**
- Gateway: router.asus.com aka **192.168.1.1**
- DNS Server: we dont really need this, just use gateway ip
    

### On PS2
- PS2 > OPL 0.9.3 > Settings > ETH device start mode > Auto
- PS2 > OPL 0.9.3 > Network config


    # assign a static ip address for our Sony PS2 console
    - PS2 -
    IP address type: Static
    IP address:      192.168.1.50
    Mask:            255.255.255.0
    Gateway:         192.168.1.1
    DNS Server:      192.168.1.1

    # connect to our Samba "ps2smb" share on PC
    - SMB Server -
    Address type:    IP
    Address:         192.168.1.100
    Port:            445
    Share:           ps2smb
    User:            [blank]
    Password:        [blank]

- PS2 > OPL 0.9.3 > Network config > Reconnect
- **Note: You should get no error message from Samba, if it failed then the settings is wrong either on PC or PS2**
- PS2 > OPL 0.9.3 > Save changes
- **Press O** to go to Game List
- **You should see a list of games**
- Finish! Pick a game and play

# Play over ethernet port (Crossover Cable Method)
- Requirements:
  - PS2
  - Crossover Cable (Most Ethernet Cable nowadays can do this also)
  - Any Computer device (Pogoplug/RaspberryPi/Laptop/PC ...etc)
- Set PS2 to static ip
- Set computer device to Static Ip (Archlinux)
    # check avalible interface name (ex: name is eth0)
    networkctl list
    
    # copy example config and rename to the interface (eth0)
    sudo cp /etc/netctl/examples/ethernet-static /etc/netctl/eth0
    
    # set static ip information (eth0)
    sudo vim /etc/netctl/eth0
    

    Description='A basic static ethernet connection'
    Interface=eth0
    Connection=ethernet
    IP=static
    Address=('192.168.1.99/24')
    Gateway=('192.168.1.1')
    DNS=('192.168.1.1')


sudo netctl restart eth0

https://archlinuxarm.org/forum/viewtopic.php?f=58&t=8045
- Setup Samba


### references
- PS2 Hard Drive Compatibility List http://ps2drives.x-pec.com/?p=list
- OPL Download files https://bitbucket.org/ifcaro/open-ps2-loader/downloads/
- Install OPL 0.9.3 https://www.youtube.com/watch?v=bWFXuB3ervo
- Pi3 OpenMediaVault PS2 https://www.youtube.com/watch?v=e0Pzp5Q3Ov4
- Install and Use FHDB 1.93 https://www.youtube.com/watch?v=lOd_1DYsIQg
- FHDB main thread http://psx-scene.com/forums/f153/unofficial-fhdb-1-93-noobie-package-obt-119562/
- HDD RAW Copy Tool http://www.hddguru.com/software/HDD-Raw-Copy-Tool/
- OpenPS2Loader 093 - Compatibility List https://docs.google.com/spreadsheets/d/1MLEw7TIKvn9MCwd5Ptbqh2lkUj3lX6YQ2wPgLEx8Koo/edit?pageId=105577267782531643387#gid=0
- OPL Settings Info http://ps2home.freeforums.net/thread/122/opl-settings-guide-tutorial
- hdl_dump Commandline Linux http://forums.fedoraforum.org/showthread.php?t=148108
- Install FMCB 1.94 From FHDB 1.93 Fat PS2 https://www.youtube.com/watch?v=ktPdYCKYFkw
- Install Free McBoot (FMCB) From Another PS2 Memory Card https://www.youtube.com/watch?v=VKYgREzpJxc
- Format HDD from PS2 HD Loader http://www.thetechloft.com/gaming/playstation-homebrew/install-a-hard-drive-in-your-playstation-2-and-format/
- HDL Dump Helper GUI 2.3 http://www.ps2-home.com/forum/viewtopic.php?t=2738



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


