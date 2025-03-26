# Armbian Package Archive (APA)

Binary deb package repository for the Armbian distribution

    echo deb https://github.armbian.com/apa current main | sudo tee /etc/apt/sources.list.d/armbian-apa.list
    wget -qO - http://fi.mirror.armbian.de/apt/armbian.key | sudo apt-key add -
    sudo apt update;sudo apt install armbian-common
