*A huge pain in the ass*
A mouse and keyboard that you can use with the Deck will make this so much easier.
Alright so, To install GTAV Rockstar version on Steam Deck:
1. Download Rockstar launcher installer either on steam deck or on a computer and then transfer it to the deck
2. Add the exe to steam as a non-steam game
3. Name this non-steam game something you will remember, it is what you are going to use to play GTA in the future. I am going to refer to it as "non-steam game" going forward.
	1. AT NO POINT DO YOU ADD ANOTHER NON-STEAM GAME FOR GTAV OR ITS LAUNCHER OR REMOVE THIS NON-STEAM GAME FROM STEAM. DOING SO WILL DELETE THE ENTIRE GTAV INSTALL.
4. Go to Properties for the non-steam game and choose the option to force it to use Proton.
	1. Choose Proton Experimental for the version
	2. I haven't tried other versions but I have had no issues with this setup
5. Run the non-steam game and install the launcher, leave checked the "Run launcher on close" option.
	1. If you unchecked this, you need to go do Step 8 and then come back here.
6. Log in with your R* account and install GTAV
	1. Choose the options to remember your credentials and auto login
7. Once GTAV has installed, close the launcher
	1. It is possible to copy the entire Grand Theft Auto V folder from your computer into the correct compatdata folder and the launcher will recognize the install automatically, if you didn't want to redownload the game.
8. Change the Target for the non-steam game
	1. Back in Steam, open Properties for the non-steam game, keep this window open
	2. Using the file explorer navigate to "home/.steam/steam/steamapps/compatdata/{code}/pfx/drive_c/Program Files/Rockstar Games/Launcher"
		1. If you can't see the .steam folder you need to enable show hidden files in the three lines menu in the top right of the file explorer.
		2. The {code} bit will be unique to you, change to list view (top left of the file explorer) and sort the list of folders in compatdata by modified. It should be the top one.
	3. Right click the Launcher.exe and click Copy Location
	4. Back in the Steam Properties for the non-steam game, paste this location. ADD QUOTES TO THE BEGINNING AND END.
	5. Then go back to the folder where Launcher.exe was and right click Launcher at the top of the explorer window.
	6. Choose Copy
	7. Return to the Steam Properties again and paste that into the Start In field.
	8. **You must do it this way.** Using the path I have written here as the target will not work because the path is different when copied in the file explorer than it is to navigate to.
9. Launch the game through steam. Make sure it launches all the way through and you can get into single player
10. Assuming everything works, you should now be able to update the non steam game again and this time make the Target PlayGTAV.exe.
	1. Follow Step 8 again and this time go into the Grand Theft Auto V folder and copy the location for PlayGTAV.exe.
	2. Update the Start In path to include the Grand Theft Auto V folder as well.
11. Now try launching the game again and this time it should load up and go straight into the game without you having to click play on the R* launcher.
	1. If you get a "Can't find the R* launcher" error, then sorry you have to keep the non-steam game target on the Launcher.exe. I got this error sometimes as well. Not sure why it happens sometimes and not others.
12. If it all works, congrats! You now have GTA working on your steam deck!

If you want to play vanilla, have fun! But if you want to spice things up with some mods, check out my tutorial on that!

[[Modding GTA V on Steam Deck]]