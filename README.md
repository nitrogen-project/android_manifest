Nitrogen OS Maintenance Manifest
====================

Create dirs, and install soft, libs
-----------------------------------

    sudo apt update
    sudo apt-get install git-core gnupg flex bison build-essential zip curl zlib1g-dev gcc-multilib g++-multilib libc6-dev-i386 libncurses5 lib32ncurses5-dev x11proto-core-dev libx11-dev lib32z1-dev libgl1-mesa-dev libxml2-utils xsltproc unzip fontconfig

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

    repo init -u https://github.com/nitrogen-project/android_manifest.git -b 13

    # Look for your device's local manifest file in this organization's page. In case of bluejay, that will be bluejay_local_manifest, so:
    git clone https://github.com/nitrogen-project/bluejay_local_manifest.git .repo/local_manifests -b 13

Clone GAPPS
---------------------------------------

    git clone https://gitlab.com/ThankYouMario/android_vendor_google_gms /vendor/google/gms -b topaz

Then to sync up:
----------------

    repo sync -j$(nproc --all)

Build command is
----------------
    . build/envsetup.sh
    lunch nitrogen_device_name-userdebug
    make -j$(nproc --all) otapackage

Official supported Devices
-----------------

    Pixel 6a (bluejay)
    Poco X3 (surya)
