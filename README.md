<p align="center">
<img src="https://github.com/Ethereal-OS/Manifest/blob/A13/assists/ETHEREAL-OS.png" > 
</p>

How to Build?
-------------
### Getting the source
Alright, so now we’re getting there. I have outlined the basics of what we’re about to do and broke them down as I know them. This is all pretty much going to be copy/paste so it’ll be fairly difficult to screw this up :)

##### Make directory for the repo binary

      $ mkdir ~/bin

##### Add directory for the repo binary to its path

      $ PATH=~/bin:$PATH

##### Downloading repo binary and placing it in the proper directory

      $ curl http://commondatastorage.googleapis.com/git-repo-downloads/repo > ~/bin/repo

##### Giving the repo binary the proper permissions

      $ chmod a+x ~/bin/repo

To initialize your local repository using the EthrealOS trees, use a 
command like this:

```bash
  repo init -u https://github.com/Ethereal-OS/Manifest -b A13 --git-lfs
```
  
Then to sync up:
----------------

```bash
repo sync -c -j$(nproc --all) --force-sync --no-clone-bundle --no-tags
```
Finally to build:
-----------------

```bash
  First You need to add the following lines in your Device Tree ethreal_devicename.mk file

  TARGET_BOOT_ANIMATION_RES := 1080 : Please change as per your device resolution

 # Inherit some common EthrealOS stuff.

for all the EthrealOS Stuff:  $(call inherit-product, vendor/ethereal/config/common_full_phone.mk)

for maintainer:  ETHEREAL_MAINTAINER := IamCOD3X

for Official:  ETHEREAL_BUILD_TYPE := OFFICIAL
(Note : It will not work untill we add that device in our git.)
 
and use the following to build:

  . build/envsetup.sh
  lunch ethreal_[device-codename]-userdebug
  make ethereal -j$
```

Help from other devices for making them Official
------------------------------------------------

If you got some commits missing in our sources for your device, let us know on our Telegram [ETHEREAL-OS](https://www.t.me/ETHEREAL_OS) </br>
Everything else, it's up to you at the time of building. </br> 

Credits
-------
* [**LineageOS/Cyanogenmod**](https://github.com/LineageOS)
* [**VoidUI**](https://github.com/VoidUI-Tiramisu/)
* [**VoltageOS**](https://github.com/VoltageOS)
* [**Thanks to all the custom rom community**]


Thanks & regards,
-----------------

#TeamEthereal

