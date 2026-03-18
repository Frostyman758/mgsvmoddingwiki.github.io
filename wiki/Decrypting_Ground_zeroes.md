---
title: Decrypting Ground Zeroes Executable
permalink: /Decrypt_GZ_EXE/
tags: [EXE, Guides, GZ]
---
## Background
For the PC release of Ground Zeroes, Valve's SteamStub DRM encrypts part of the game's executable on disk. This can be reversed using Steamless, an open-source unpacking tool, to produce a fully functional decrypted executable usable for Ghidra analysis and debugging. The setup is pretty simple, head
  over to the [Steamless](https://github.com/atom0s/Steamless) Github page and extract the latest release. For this guide, I will use the gui-based version of steamless. 

## Steps

1. Launch `Steamless.exe` and point the file path to your Ground Zeroes install directory, selecting `MgsGroundZeroes.exe`.

2. Select the following options:

   -  Keep Bind Section
   -  Don't Realign Sections
   -  Zero DOS Stub Data
   -  Dump SteamDRMP.dll To Disk

3. Click **Unpack**. Steamless will output a decrypted executable in the same directory.

4. Test the output executable, should run perfectly fine afterwards. 
## Photo of correct options in the gui


## 
With a working decrypted executable, the next steps are removing the remaining anti-debugger detection and decoupling the parent/child process relationship that the game normally establishes. That being said, for Ghidra research, this is all that is required. 
