<h2 align="center">
  <a href=#><img src="https://raw.githubusercontent.com/armbian/.github/master/profile/logosmall.png" alt="Armbian logo"></a>
  <br><br>
</h2>

### Purpose of This Repository ###

This repository serves as the **Armbian Package Archive (APA)** — a binary `.deb` package repository tailored specifically for the Armbian distribution.

Unlike general-purpose build systems such as Launchpad or Open Build Service (OBS), this repository is **not intended as a universal publishing platform**. Instead, it focuses on **hardware enablement and system integration for single board computers (SBCs)** supported by Armbian.

The primary goal of APA is to:

- **Simplify software packaging and distribution** for Armbian users and developers
- **Collect, standardize, and publish** packages that require specific integration or coordination with Armbian’s kernel, bootloader, or base system
- Ensure that **packages work correctly together** in the Armbian ecosystem

Packages are published at: [https://github.armbian.com/apa/](https://github.armbian.com/apa/)

This repository contains metadata, package configurations, and publishing logic to support automated and consistent package delivery to Armbian-based systems.

### How to build locally ###

On a Debian-based system

    sudo apt install devscripts debhelper fakeroot
    git clone git@github.com:armbian/apa.git
    cd apa
    debuild -uc -us

### How to use on your SBC ###

    echo deb [trusted=yes] https://github.armbian.com/apa current main | sudo tee /etc/apt/sources.list.d/armbian-apa.list
    sudo apt update
    sudo apt install armbian-common

### Philosophy ###

This repository defines and provides a number of (virtual) armbian-* packages.  For example, there are a
few armbian-desktop-* packages to aid in getting different desktop environments safely installed and
running.  Board- and arch-specific packages are another common package.

Packages in Depends: cannot be uninstalled as long as the meta-package in question resides on the host
computer.  Packages in Recommends: and Suggests: will be kept installed if they already are but they can be
removed manually or if a package conflict requires it.  Packages in Suggests need to be manually selected
for installation.  Packages in Recommends: can be configured to be installed automatically.

Packages from Depends of armbian-common define Armbian minimal images (network, sshd and succesful boot).
Adding the Recommends defines the CLI images.  Desktop image flavors include both Depends and Recommends
from their respective meta packages.
