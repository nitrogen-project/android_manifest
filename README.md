Nitrogen OS Manifest
===================

Create dirs, and install soft, libs
-----------------------------------

    sudo su
    apt-get install bison build-essential curl flex lib32ncurses5-dev lib32readline-gplv2-dev lib32z1-dev libesd0-dev libncurses5-dev libsdl1.2-dev libwxgtk2.8-dev libxml2 libxml2-utils lzop openjdk-7-jdk openjdk-7-jre pngcrush schedtool squashfs-tools xsltproc zip zlib1g-dev git-core make phablet-tools gperf
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

    repo init -u https://github.com/nitrogen-project/android_manifest.git -b n
    

Then to sync up:
----------------

    repo sync

Build command is
----------------

    cd ~/nitrogen
    . builder.sh

Official supported Devices
-----------------

   LG Optimus G - E975/F180/LS970 GEEHRC/GEEHRC4G/GEESPR - xyyx, Mr.MEX

   Google Nexus 4 - E960 MAKO/OCCAM - Mr.MEX

   Google Nexus 5 - D820/D821 HAMMERHEAD - Mr.MEX

   Google Nexus 6 - XT1100 SHAMU - Ajdin
