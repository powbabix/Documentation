# Steps taken to setup Jasper after a fresh image install. 

_MattCurry.com Images Only_

DO NOT USE POPULATE.PY

The default setup requires an internet connection.

* Prepare the OS
  * Setup Wifi (Check out [Raspberry Pi documentation link](https://www.raspberrypi.org/documentation/configuration/wireless/wireless-cli.md) to know more)
  * Open the PI’s configuration screen (in the terminal window) by typing: `sudo raspi-config`
    * Under the `Boot Options` menu, select the "Wait for network at boot" option and ensure it is set to `Yes`
    * Under the `Advanced Options` menu, scroll down to run the bottom `update` option just to make sure you have the latest version of raspi-config
    * Run the `Expand Filesystem` option to Expand SD Card
    * Under the `Advanced Options` menu, choose `Memory Split` to update the amount of memory available to the GPU
      * Set it to 16
    * Under `Internationalisation Options` choose the option to `set locale` and select your desired locale
    * Under `Internationalisation Options` choose the option to `change keyboard` and choose your desired keyboard layout
    * click: `Finish` then select `Yes` when it asks for a reboot

* [Install the Jasper REPO](installation.md)
  * During script execution, choose desired branch
    * Master
    * Jasper-Dev

* Choose STT (Speech To Text) engine
  * Wit.ai is installed and set as default STT engine already. No steps required if you wish to leave as is.
   * You will need to go to wit.ai and obtain a server token for it to work
   * Once you have the server token, run `sudo nano ~/.jasper/profile.yml` and overwrite the placeholder text for the token
   * Enter `ctrl + x` to exit the file, selevting `yes` and `enter` to save the file contents

* Choose TTS (Text To Speech) engine
  * MaryTTS (aka Fatts) is installed and set as default TTS engine already. No steps required if you wish to leave as is.
    * Runs on a hosted community TTS server, no token required for setup

* Set up other parameters in profile
  * Run `sudo nano ~/.jasper/profile.yml` to edit the profile file
  * Overwrite the `gmail_address` and `gmail_password` with your own details to allow email inbox reading
    * Note that the first time this tries to connect, it may trigger an authentication warning with Gmail. Log in to gmail to and view the notification email to allow access.
  * Overwrite `first_name` and `last_name` with your own details
  * Overwrite `location` with your own location (Zip Code or Post Code) to get weather updates etc.
  * Overwrite `timezone` with your own timezone, in correct format from [here](http://www.timeanddate.com/time/zones/)

At the terminal, run `sudo reboot` to reboot the Pi.  On startup, you shoudl see the jasper-daemon successfully start, in which case Jasper is on and listening to your every word.

If you want to monitor more closely, type `/home/pi/jasper/jasper.py' to see a more interactive output which displays what you say as you say it.

From here on, standard Jasper documentation should apply.  Find it [here](http://jasperproject.github.io/documentation/)