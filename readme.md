### This Repo is for testing, and updating to work with New Twitch Helix API 
====

This is a stripped down version of the SteamVR Unity Plugin with a custom Overlay script that displays twitch chat!

#### Oculus Rift users:
We're receiving reports that some Rift users find some games are incompatible with the SteamVR Overlay system. You can read more about it in [the issue posted here](https://github.com/Hotrian/OpenVRTwitchChat/issues/4). The jist of things is that some games seem to skip the SteamVR Compositor and draw directly to the Rift instead. Check the SteamVR Display Mirror and see if you can see the Overlays there. If you can see the Overlays in the Mirror but not the Rift, then that game is probably incompatible :(. Please post your findings in [the issue](https://github.com/Hotrian/OpenVRTwitchChat/issues/4).

## Features
- See your favorite Twitch.tv chat in VR! From _almost_ any SteamVR game!
- Easily attach Chat to the Screen, a Tracked Controller, or drop it in the World.
- Easily snap Controller attached Chat to a set "Base Position".
- Offset Chat positionally and rotationally.
- Basic Gaze Detection and Animation support (Fade In/Out and/or Scale Up/Down on Gaze).
- Basic Save/Load Support! Saves all settings _except_ OAuth Key!
- Notification Sound on Chat Message Received (Set Volume to 0 to Disable)
- Active Viewer Count (Updated as often as Twitch allows)
- "Experimental" Emote Support ;) ![kappa](http://static-cdn.jtvnw.net/emoticons/v1/25/1.0) ![kappa](http://static-cdn.jtvnw.net/emoticons/v1/25/1.0)

## Basic Controls
(click to enlarge) (actual controls might vary slightly as this is still under development)
![basic controls](http://image.prntscr.com/image/224cbd14d02f4e209879ef9d5f647be2.png)


## Known Issues
- SteamVR_ControllerManager.cs doesn't correctly auto-identify controllers for me, so I wrote my own manager, HOTK_TrackedDeviceManager.cs. My Device Manager is super pre-alpha but should correctly identify both Controllers as long as at least one of them is assigned to either the left or right hand, and they are both connected. If neither Controller is assigned to a hand, they are assigned on a first come first serve basis. If only one Controller is connected, and it isn't already assigned, it will be assigned to the right hand.
- Oculus Rift Users are reporting some games seem to be incompatible, please see [the issue posted here](https://github.com/Hotrian/OpenVRTwitchChat/issues/4).
- If you launch it and nothing happens in VR, check the Data folder for output_log.txt and look for "Connect to VR Server Failed (301)" if you're getting that error, try restarting your PC, and if that doesn't work [try this solution](https://www.reddit.com/r/Vive/comments/4p9hxg/wip_i_just_released_the_first_build_of_my_cross/d4kmvrj) by /u/GrindheadJim:

>For clarification, what I did was right-click on the .exe file, clicked "Properties", went to the "Compatibility" tab, and checked the box under "Run as Administrator". For the record, I have also done this with Steam and SteamVR. If you're having any issues with any of these programs, I would start there. 

## Additional Notes / Tips & Tricks
- When attaching Overlays to controllers, the offset is reoriented to match the Base Position's orientation. X+ should always move the Overlay to the Right, Y+ should always move Up, and Z+ should always move Forward, relative to the Overlay.
- You can copy and paste your OAuth key, you don't have to manually type it out, but you do have to get it off that site, or off another site that generates Twitch OAuth keys.
- OAuth is not saved for security reasons.
- You can put the Overlay up in the sky and tilt it if you don't like it on the controllers and find it obtrusive in the world. Just set the Base Position to "World", then mess with the middle "Positional Control" slider and the top "Rotational Control" slider until you find a position that works for you :)
- You can stream the Display Mirror if you want your viewers to be able to see the Overlay, or you can stream the game's output if you do not.
- To save a new settings profile, select "New.." from the dropdown and press "Save", then enter a name in the box just below and press the new "Save" button.
- To delete a profile, select the profile you want to delete from the dropdown box, and click the Delete button twice. On the first click the text will change red and the tooltip will change. On second click the profile will be deleted. There is no undo so use this wisely. Select a different profile or press Load or Save to reset the Delete button.
- You can disable Chat Notification Sounds by setting the Volume slider to 0.
