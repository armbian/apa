# Armbian Package Archive (APA)

Binary deb package repository for the Armbian distribution

## How to build locally ##

On a Debian-based system

    sudo apt install devscripts debhelper fakeroot
    git clone git@github.com:armbian/apa.git
    cd apa
    debuild -uc -us

## How to use on your SBC ##

    echo deb [trusted=yes] https://github.armbian.com/apa current main | sudo tee /etc/apt/sources.list.d/armbian-apa.list
    sudo apt update
    sudo apt install armbian-common
