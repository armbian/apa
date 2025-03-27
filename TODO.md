Taks list

- [ ] Extract Existing Desktop Configurations
  - identify the installed desktop environment packages and configurations:
  - copy necessary configuration files and settings
  - include any additional scripts, themes, and optimizations
  - transfer meta-data and functionality from current scripts
    - [armbian-base-files](https://github.com/armbian/build/blob/main/lib/functions/artifacts/artifact-armbian-base-files.sh)
    - [BSP packages](https://github.com/armbian/build/blob/main/lib/functions/artifacts/artifact-armbian-bsp-cli.sh)

- [ ] Implement proprietary drivers

Ideally, create new arch-dependendent packages to properly reflect and support the large number of different hardware
  - depending on variable set in /etc/armbian-image For example - add certain blobs for RK3588, Genio, ...
    -> that is what the collection of armbian-bsp virtual packages do

- [ ] Automating Assembly

Write action script to package desktop environment.

- [x] Automate Repository Generation

  - ~~Create a script to generate a local repository similar to https://github.com/armbian/armbian.github.io but here we can have apt.armbian.com or deb.armbian.com or archive.armbian.com.~~

- [ ] Integrating with armbian-config

  - Add support for fetching desktop environments from the new repository.
  - Update the armbian-config script to fetch packages from the new repository.

- [ ] Testing & Deployment

  - Use automatic testing facility that is a part of armbian-config repository
  - test debian/changelog for syntax
