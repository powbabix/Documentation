# Steps taken to setup Jasper after a fresh image install. 

_MattCurry.com Images Only_

The default setup requires an internet connection.

* Prepare the OS
  * Setup Wifi ([ visit Raspberry pi documentation link](https://www.raspberrypi.org/documentation/configuration/wireless/wireless-cli.md))
  * Open the PI’s configuration screen (in the terminal window) by typing: `sudo raspi-config`
  * Run the bottom option just to make sure you have the latest version of the configuration software: `update`
  * Run the second option to Expand SD Card: `expand_rootfs`
  * Update GPU Memory
    * Set to 16
  * Setup Locale
  * Setup Keyboard
  * click: `Finish` select `YES` when it asks for a reboot.  

* [Install the Jasper REPO](installation.md)
  * Choose Branch
    * Master
    * Jasper-Dev
* Choose STT
  * Wit.ai (Default)
   * Obtain Server Token from wit.ai
* Choose TTS
  * MaryTTS (aka Fatts)
    * Community TTS Server
