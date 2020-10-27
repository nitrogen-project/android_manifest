Nitrogen OS Maintenance Release 2 Manifest
====================

Create dirs, and install soft, libs
-----------------------------------

    sudo su
    apt update
    apt install repo git gnupg flex bison gperf build-essential zip curl zlib1g-dev gcc-multilib g++-multilib libc6-dev-i386 libncurses5 rsync lib32ncurses-dev x11proto-core-dev libx11-dev lib32z1-dev libgl1-mesa-dev libxml2-utils xsltproc unzip fontconfig
    exit

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

    repo init -u https://github.com/nitrogen-project/android_manifest.git -b 11
    # Look for your device's local manifest file in this organization's page. In case of oneplus3, that will be oneplus3_local_manifest, so:
    git clone https://github.com/nitrogen-project/oneplus_local_manifest.git .repo/local_manifests -b 11

Then to sync up:
----------------

    repo sync -j$(nproc --all)

Build command is
----------------
    . build/envsetup.sh
    lunch nitrogen_oneplus3-userdebug
    make -j 7 otapackage

Official supported Devices
-----------------

    OnePlus 3 (oneplus3)
    Poco X3 (surya)
