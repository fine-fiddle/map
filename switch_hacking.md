# Switch Hack

## Main Notes.
1. [NH Homebrew Discord Guide](https://nh-server.github.io/switch-guide/) They're anti-piracy, but maybe the only wiki that stays up to date.
   1. [Other Wiki](https://switch.homebrew.guide)

## Common Problems
1. Sigpatches
   1. As of 2021-02, [the AIO (all in one) updater](https://github.com/HamletDuFromage/AIO-switch-updater/releases/) seems to be the best way to acquire sigpatches, update SwitchOS, and update CFW
   2. A problem here should be addressed by wiping the atmosphere and sept folders.
   3. [sigpatches gbatemp thread](https://gbatemp.net/threads/sigpatches-for-atmosphere-hekate-fss0-fusee-secondary-only.571543/)
   4. There are different types of sigpatches depending on something i don't understand about fusee-primary or fusee-secondary.
2. Archive bit
   1. [Hekate can do it](https://birbchirp.gitbook.io/switchguide/misc-useful-stuff/hekate-archive-bit)
   2. `sudo chflags -R arch /Volumes/[name of SD card]/[name of file or folder]` [source](https://apple.stackexchange.com/questions/248333/how-to-change-fat32-file-attributes-under-os-x)
   3. Brew install mattrib
      1. `mattrib a- /Volumes/Card` (i didn't get this working)
   4. Mac Resource Fork Dotfiles on Fat32
      1. [autodelete?](https://apple.stackexchange.com/questions/26124/autodeleting-resource-forks-on-fat-disks)
3. Tinfoil NSP install Errors
   1. In Tinfoil Options, there is a way to allow installation of unsigned code. Seems necessary?
   2. If you have the wrong sigpatches, gotta delete atmosphere and maybe nyx/sept or something.
4. modules can be incompatible with new CFW or Switch OS causing all sorta difficult to diagnose issues.

## Techniques
### Splitting NSPs
- "You need to put all splits into one single folder and set the Archive bit for this folder (rightclick, properties, archive checkbox). Goldleaf will then recognize the folder as an installable NSP."
- [Python Script](https://github.com/AnalogMan151/splitNSP)
- `split -a 2 -b 4000m game.nsp outputnamebeforeprefix`

## 2021-01-06
### Problems
- 10.16 macs don't see switch in RCM
- Launch > Fusee:
  - Hekate IPL > sept by atmosphere > atmosphere > "A" black and white logo > Nintendo switch logo (not at full brightness)
    - Error 2168-0001 (0x2aB) including "A" color logo upper right.
    - program 420000000007e51a
    - firmware 10.1.0 (Atmosphere m 0.18.0-master-26d8db74)
- Launch > CWF (sysMMC)
  - Hekate  - ipl > " A" black n white logo > Nintendo switch logo (not at full brightness)
    - Error 2168-0001 (0x2aB) including "A" color logo upper right.
    - program 420000000007e51a
    - firmware 10.1.0 (Atmosphere m 0.18.0-master-26d8db74)

### Theories
- Figure out difference between `Launch > Fusee` and `Launch > CFW(sysMMC)`
- Ask in Discord??

### Solution.
- there are two forms of sigpatches now, relating to booting with fusee primary or fusee secondary.
- goldleaf didn't support the version of switchOS to wich i had graded.
- sdsetup is no longer trusted by the nh-server people, and i think it was giving me out of date or screwy software.

## Old Notes from Apple Notes

```text
- TegraRCMGUI for windows
- fusee-launcher for Mac
  - Python 3
  - Pip3 install plush
    - Brew install libusb (not needed?)

HBmenu won’t see files with archive bit set (happens on Mac?)

=> n1dus
- https://github.com/zhaoloving/n1dus
  - Info about keys
  - https://github.com/shchmue/Lockpick

SIGPATCHES
- https://gbatemp.net/threads/tinfoil-now-with-network-install.515932/
  - Tinfoil instructions have a few words
- https://www.reddit.com/r/SwitchPirates/comments/9vu7br/nsps_not_starting_newbie_here_but_its_so_confusing/
  - Has the actual info
https://www.google.com/search?q=how+to+create+ips+patches&oq=how+to+create+ips+patches
https://reinx.guide/faq
https://www.reddit.com/r/SwitchPirates/comments/93crtn/atmosph%C3%A8re_sig_patches_20_direct_download200_510/

https://darkumbra.net/forums/topic/181136-nintendo-switch-firmware-files-100-latest/

Switch firmwares
https://darthsternie.net/index.php/switch-firmwares/
https://team-xecuter.com/community/threads/nintendo-switch-official-firmwares.129233/

Install program
https://switchtools.sshnuke.net

Dump Keys
https://github.com/shchmue/Lockpick


XCI = cart backup. NSP is the “install game” like CIA



~~~~~~~~~~~~
2020 Tips


Next Steps for Kirts? 
-     ? 
- Restore from backup? 

Restore Nand on Kirt’s?
https://nh-server.github.io/switch-guide/extras/nandrestore/
Restore switch serial? https://birbchirp.gitbook.io/switchguide/tinfoil-stuff/tinfoil-incog-hub/tinfoil-incognito

Birb Guide has good info:
https://birbchirp.gitbook.io/switchguide/

New Freeshop?
https://www.reddit.com/r/SwitchPirates/comments/gkf7q4/just_insert_the_stuff_the_new_jits_aio/
```
