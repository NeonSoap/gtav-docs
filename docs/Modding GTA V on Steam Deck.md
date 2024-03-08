This guide assumes you have enough knowledge modding GTAV to be able to set up the essential mods (trainer, scripthookv, gameconfig, addon cars, etc) on a Windows install.
If that is all gibberish to you please use the resources below before continuing with this tutorial: 
* [Basics of GTAV modding](https://www.youtube.com/watch?v=N0ovURiaTtE)
* [How to install replacement mods (Easy way)](https://gtaforums.com/topic/870069-v-how-to-create-a-own-dlc-for/). Highly Recommended.
	* This is a much simpler way to install mods that replace content than the way the video above describes.
# Disclaimers
* I am using the R* launcher version of GTAV, I don't know how to do this for Steam or Epic versions. I would assume that both use similar principles though.
* I have GTAV installed on the internal SSD on the Steam Deck, I'm not using an sdcard.
* I am using an external hard drive to transfer files between the Steam Deck and my computer. I have been able to get OpenIV running on the steam deck but actually using it on there is a pain in the ass.
# Recommendations
1. I would highly recommend installing GTAV on either your personal computer or directly on an external drive that you can also use to transfer files between your computer and Steam Deck. This will allow you to run your modded install of GTA on your computer as a sanity check to see if things aren't working because of the mods or because of the Deck itself.
2. If you are able to, I recommend installing GTAV on your internal SSD on the Deck, that is how I have done it and it is working perfectly. There are people who have gotten all this working with the game on an sdcard but it takes some extra steps and I can't shed any light on them.
# How Steam Treats Non-Steam games
Let me start off by saying that this whole set up process is very similar to the process on Windows except that you need to treat the launcher you added to steam as a non-steam game as the way you launch any and all programs related to GTAV and mods.
## Why?
Basically, because steam creates a different folder in *home/.steam/steam/steamapps/compatdata/* every time you add a non-steam game to it, this means that if you want to install or run another program and have it see your GTAV folder, you have to run it through that first non-steam game you added. Otherwise it will be as if you installed that program on another computer entirely. Think of each folder inside /compatdata/ as the folder system of a different computer, because that is basically what they are.

So to get around this behavior, any additional programs need to be installed by changing the target of the original non-steam game that you added (in this case, the one that you created to install the R* launcher). This ensures that the tools are installed into the correct steamapps folder.

# Modding Methods
There are four main ways to mod GTAV on the Deck using OpenIV. Each differ based on where OpenIV is installed and how it is accessing your GTAV files. Below is a comparison of each.
## The "Windows Computer" Method \[Recommended for heavy modding]
Here you install OpenIV and GTAV on a Windows computer, modify the files there and then copy the modified ones to the Deck.
Pros:
* Offers the most modding freedom.
* No worries about compatibility/trying to get OpenIV or other modding utilites working, they just do since its on Windows.
* The ability to sanity check your work by launching the game on the Windows computer.
* The ability to play and identical version of your modded GTA on computer, should you want to
Cons:
* Requires a lot of repetitive work
* Requires a Windows computer
* Requires an external usb stick at least 10gig in size
* Is annoying to transfer files and make sure you are putting them in the right places
## The "External Drive" Method \[What I did]
Here you install GTAV entirely on an external drive, and use that to both mod and transfer files. You install OpenIV on a Windows computer and mod the game there.
Pros:
* The same pros as the "Windows Computer" method
Cons:
* Same as "Windows Computer" method, except:
* Instead of a >10gig usb, you need an external drive at least big enough to hold GTAV ~115gig + whatever mods you want.
## The "Remote" Method \[Recommended for light modding]
This method has you run OpenIV on another computer and access the Deck's files remotely using its built in SSH server.
Pros:
   * You only have to do stuff once
   * Doesn't require any external usb drives or copying files between then
   * It is wireless
   * Don't have to install GTA in multiple places
   * No worries about compatibility/trying to get OpenIV or other modding utilites working, they just do since its on Windows.
Cons:
   * Might not work for all modding tools and you might have to fall back on one of the other methods
   * Is slower than other options since it is wireless
   * Can open your Deck up to hackers if you forget to shut down the SSH server on it before connecting to public WiFi
   * Can be a little unstable (again wireless)
### Notes on this method
If you do decided to use this method, follow this tutorial: [Reddit tutorial](https://www.reddit.com/r/SteamDeck/comments/165ildh/how_to_install_mods_in_gta_5_on_steam_deck/).
To add some context for what they are describing in that post the following links are helpful:
* [More detail on enabling SSH server](https://shendrick.net/Gaming/2022/05/30/sshonsteamdeck.html)
* [SSHFS Tool for Windows](https://github.com/winfsp/sshfs-win)
On Windows 10 you have to right click the Network option in Explorer and choose Map a Network Drive from there.
The tutorial says to mount only /home/deck/ and then access your GTAV install from there, that didn't work for me. Instead I mounted: `\\sshfs.r\deck@{hostname}\home\deck\.steam\steam\steamapps\compatdata\{your folder code}\pfx\drive_c\`
This gets you directly into the area where GTAV is installed.

## The "Local" Method \[Not Recommended]
You install OpenIV and any other modding tools directly on the Deck and do all your modding there. Not even going to do a Pro/Con list for this one because honestly, while it seems like the most logical option, I really only recommend it if you can throw it in a dock and use an external monitor, keyboard etc and you are comfortable using the Deck in its Desktop Mode. I have tried using OpenIV on the deck and yes, you can, but if you are trying to use the built in screen you are going to develop back problems and eye problems.

This guide will focus on the first two but the principles will be the same for all the methods.

I know, its a lot. But I promise the process isn't too difficult. It is 90% making sure that you copy the right files to the right places, 10% voodoo magic.

# Let's F\*\*\*ing do this thing \[Methods 1 & 2]
## You will need a...
* Working, vanilla GTAV install on the Deck
* Working, vanilla GTAV install on Windows
* External hard drive with a separate GTAV install on it (Method 2)
* USB drive to transfer files (Method 1)
* ..nother computer
* Lot of patience
## Steps
### 1. Install and test your mods
Using your knowledge or the resources linked above, install:
* OpenIV
* menyoo
* scripthookv
* an addon car mod
If you want, you can do more (heap adjuster, gameconfig, etc), I'm just listing these as a minimum, but the more you add now the more you will have to copy over to the Deck the first time and the more that can go wrong.

Make sure they are all working on Windows before continuing!
### 2. Copying Mods to the Deck
Now that you have a working GTAV install we need to set it up on the Deck. Note that you only have to do all these once. When you add mods in the future you only have to copy the files that changed.
#### Copy the following to the Deck according to the table
Put your Deck in Desktop Mode (duh).
In the table below "/" means your main GTAV install folder on the Deck. It is shorthand for: */home/.steam/steam/steamapps/compatdata/{code}/pfx/drive_c/program_files/Rockstar Games/Grand Theft Auto V/*
Also note that where you put files on the Deck is the same place you get them from on Windows, inside the main GTAV folder.

| Mod         | file/folder name | place in |
| ----------- | ---------------- | -------- |
| OpenIV      | openiv.asi       | /        |
| OpenIV      | dinput8.dll      | /        |
| ScriptHookV | ScriptHookV.dll  | /        |
| Menyoo      | Menyoo.asi       | /        |
| Menyoo      | menyooStuff      | /        |
| Addon mods  | mods             | /        |
That's it! Not too bad.

### 3. Setting Deck Launch Options
This part is very important and specific to the Steam Deck. Not following these instructions exactly will cause things not to work.

1. Still in Desktop Mode, open Steam (NOT Return to Gaming Mode)
2. Find the GTAV non-steam game that you made from the original install
3. Click the Gear, then Properties
4. In Launch Options set: `WINEDLLOVERRIDES="dinput8.dll=n,b" %command%`
	1. This must be set exactly as it appears above
5. Close the Properties window
### 4. Launch!
Now is the time to test if all your hard work as paid of. 
1. Return to Gaming Mode and launch the game
2. Perform the following tests:
	1. Load into single player
	2. Open Menyoo (RB+Left on dpad)
	3. Spawn the modded car you added
		1. To do so, go to the Vehicle Spawner and at the bottom of the list choose Input
		2. Type in the name of the vehicle you added (Keyboard is: Steam Button + X)
			1. Consult the video above if you don't know how to find the car name
	4. Drive over some pedestrians in celebration
If you were able to complete all the test successfully, congratulations! You now have a modded GTAV install on your Deck and a solid base to add to.
If something broke, sorry... Head to the Troubleshooting section below.
### Troubleshooting
#### You can't launch the game or you get can't find R* launcher error
If it was launching fine before the modding process:
1. Check the Target field in the non-steam game for GTAV
	1. It needs to be set to either Launcher.exe or PlayGTAV.exe, if it is set to one, try the other.
	2. The path needs to be of the form: */home/deck/.steam/steam/steamapps/compatdata/{code}/pfx/drive_c/Program Files/Rockstar Games/Grand Theft Auto V/* followed by either .exe. Obviously {code} is replaced with whatever the long number folder name is in your case.
	3. Make sure the whole path is surrounded by double quotes. VERY EASY TO MISS, VERY IMPORTANT.
2. Check the Start In field and make sure it is pointed to the directory that contains the exe in the Target field. For example: */home/deck/.steam/steam/steamapps/compatdata/{code}/pfx/drive_c/Program Files/Rockstar Games/Grand Theft Auto V/*
	1. Again. {code} is replaced with whatever you folder code is
	2. This path does not need double quotes
If you didn't try launching the game before starting to mod you are a very bad boy and I can't help you. Welcome to what happens when you skip steps.
#### You can load into the game but can't open menyoo
1. Make sure that you have all the files from Step 2 in your main GTAV folder
2. Ensure that you set the launch option correctly in Step 3
#### You can open menyoo and use it but you cant spawn the car
1. Most importantly, make sure you are typing in the correct name. It is usually the name of the folder that you put into /dlclists/.
2. Make sure that you have all the files from Step 2 in your main GTAV folder
	1. Make especially sure that OpenIV.asi is in your GTAV folder. Yes it is possible for menyoo to work but OpenIV not to load mods.
### 5. Enjoy!
If you got to the end here and everything is working, honestly congratulations, this is a pain in the ass. Take a break by playing your newly modded game!

If you want to go deeper into modding I have some notes below on getting different kinds of mods working on the Deck.