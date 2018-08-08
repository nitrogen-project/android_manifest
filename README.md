Nitrogen OS Maintenance Release 2 Manifest
====================

Create dirs, and install soft, libs
-----------------------------------

    sudo su
    add-apt-repository ppa:openjdk-r/ppa
    apt-get update
    apt-get install bison build-essential curl ccache flex lib32ncurses5-dev lib32z1-dev libesd0-dev libncurses5-dev libsdl1.2-dev libxml2 libxml2-utils lzop pngcrush schedtool squashfs-tools xsltproc zip zlib1g-dev git-core make phablet-tools gperf openjdk-8-jdk
    exit
    
    
Install repo
------------

    mkdir ~/bin
    PATH=~/bin:$PATH
    cd ~/bin
    curl http://commondatastorage.googleapis.com/git-repo-downloads/repo > ~/bin/repo
    chmod a+x ~/bin/repo
    

Create nitrogen folder
----------------------

    mkdir ~/nitrogen
    cd ~/nitrogen
    

GIT config (nickname, e-mail)
-----------------------------

    git config --global user.email "mail@domain.com"
    git config --global user.name "login"
    

To initialize your local repository use
---------------------------------------

    repo init -u https://github.com/nitrogen-project/android_manifest.git -b p
    

Then to sync up:
----------------

    repo sync -j 16

Build command is
----------------
    . build/envsetup.sh
    lunch nitrogen_oneplus3-userdebug
    make -j 7 otapackage

Official supported Devices
-----------------
