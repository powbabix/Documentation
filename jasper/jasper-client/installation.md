#Install Jasper Repo

There will be a folder in home called "Jasper-RPI-Tools"; this has many useful items in it.

To get started the Jasper Repository will need to be cloned.

*To do so follow the example below:

    cd
    cd Jasper-RPI-Tools
    git pull
    cd installers
    ./jasper-repo-installer.sh


Just follow the prompts, the daemon is expecting it under /home/pi/ with user pi.  If you change this, you will have to update the daemon, and correct the path.

    Jasper - /etc/init.d/jasper-daemon
