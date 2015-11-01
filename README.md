# oot3dhax_installer
Erm, can I use OoT3D instead of Ironfall? The answer is probably yes.

With expressions of severe indebtedness to smea and yellows8.

***This repository is no longer maintained.*** Try [this one](https://github.com/phase/oot3dhax_installer) instead.

## Instructions:
* (Optional) Backup and then wipe your OoT3D saves (start from home menu, hold down ABXY). The installer will not do this for you.
* Put .smdh, .xml, .3dsx files in sd:/3ds/ootsdhax_installer/, along with the save0x.bin.* files (optionally just the one for your region). Just download the 3ds directory from the repo and move the folder appropriately.
* Open installer via tubehax or other *hax. Make sure to select OoT3D as the target app. (If you don't see a target selection screen, exit and restart.) Follow instructions.

## Troubleshooting
I can't support this, but there are a few quick pointers:
* Check you have all the required files (especially the save0x files) in the correct directory.
* Check that you have a working internet connection, since the installer downloads the payload from smea.
* If all else fails, try wiping the OoT3D save data. Again, the installer won't do this for you.

The installer has been tested on a 9.9 O3DS(XL) (USA). The saves have been tested for USA O3DS 9.9 and JPN N3DS 9.9. <a href="https://gbatemp.net/threads/quick-and-dirty-oot3d-port-of-ironhax-installer.396312/#post-5647053">I have a report of the install working on a EUR 9.9 N3DS.</a> <a href="http://gbatemp.net/threads/quick-and-dirty-oot3d-port-of-ironhax-installer.396312/#post-5647329">I also have a report of the install working on a USA 9.0 N3DS</a>, so I'm guessing this is working for all ninjhax2-compatible 3DS units. eShop versus gamecard should be irrelevant, as long as you can select OoT3D as the target app when launching the installer.

## Quick overview
We already have all the pieces in place:
* smea's sploit_installer, which downloads ninjhax2 otherapp payloads
* smea's oot3dhax fork from yellows8, which works

So it's just a matter of making it use OoT3D saves instead of ironhax saves. If you wanted to use regionFOUR or ninjhax1 payloads and fetch them either from a different URL or from the SD card, there's nothing stopping you as long as those payloads support otherapp (which the ironhax payloads do, since they're built for apps that aren't Cubic Ninja).

One optional item we would like:
* a quick modification that should let us load payload from SD card, not gamecard

This last one is necessary because OoT3D apparently isn't made of free save partition space, and can't hold both a ninjhax2 payload and more than one save file. ironhax apparently has a similar problem, since the ironhax installer does compress the payload before writing it to save data. However, if we can just load the payload from the SD card, this makes our lives easier. A few dozen kilobytes isn't much to ask from an SD card these days.
