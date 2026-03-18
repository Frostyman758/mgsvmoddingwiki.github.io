---
title: Decrypting Ground Zeroes Executable
permalink: /Decrypt_GZ_EXE/
tags: [EXE, Guides, GZ]
---

For the PC release of Ground Zeroes on PC, Konami decided to implement steam DRM, which encrypts part of the game's executable. Fortunately for us, we can use tools to decrypt the exe for ghidra research and disable the anti-debugger detection. While this may not be as straight forward as downloading an exe from steam, the steps are pretty simple.

Head to the github page for steamless, a drm removal tool (note this does not allow for piracy, just the decryption of the exe) and download the latest version. for ease of guide, I have linked it here(https://github.com/atom0s/Steamless)

I will use the the gui version, 'steamless.exe' since I think it's the easiest way to demonstrate what to do. Once you launch the exe, point the file path to your GZ instal directory, then please select the following options to ensure you receive a functioning exe. 
* Keep Bind Section
*  Don't Realign Sections
*  Zero DOS Stub Data
* Dump SteamDRMP.dll To Disk

Now click unpack, the tool should output a fully decrypted exe which both runs and can be imported into Ghidra for research purposes. Test the exe, make sure it runs. 

The next steps after this for is to remove the the parent/child process setup and remove the remainder of the anti-debugger detection, but for just browsing in Ghidra this should work. 


