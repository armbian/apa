# Armbian Package Archive (APA)

Binary deb package repository for the Armbian distribution

## How to build locally ##

On a Debian-based system

    sudo apt install devscripts
    git clone git@github.com:armbian/apa.git
    cd apa
    debuild -uc -us
