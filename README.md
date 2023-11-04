# flatpak-example-gtkdemo

This is a GTK demo application in flatpak


## Setup

### Install flatpak

Please follow Flathub's [setup](https://flathub.org/setup) for your OS distribution.

### Install flatpak-builder for building flatpak

Each OS distribution has **flatpak-builder** package:
* Alpine: `apk add flatpak-builder`
* Arch Linux: `pacman -S flatpak-builder`
* Debian: `apt install flatpak-builder`
* Fedora: `yum install flatpak-builder`
* Ubuntu: `apt install flatpak-builder`
* ...


## Build

1. Get repository:
   ```
   git clone https://github.com/starnight/flatpak-example-gtkdemo
   ```
2. Install SDK.  The flatpak-example-gtkdemo uses GNOME 45 runtime now:
   ```
   flatpak install flathub org.gnome.Sdk//45
   ```
3. Build & package as flatpak **io.github.starnight.gtkdemo** application with the manifest:
   ```
   flatpak-builder build-dir build-aux/flatpak/io.github.starnight.gtkdemo.yml --force-clean --install --user
   ```
4. Show flatpak **io.github.starnight.gtkdemo** application:
   ```
   $ flatpak info io.github.starnight.gtkdemo
             ID: io.github.starnight.gtkdemo
            Ref: app/io.github.starnight.gtkdemo/x86_64/master
           Arch: x86_64
         Branch: master
         Origin: gtkdemo-origin
     Collection:
   Installation: user
      Installed: 16.4 kB
        Runtime: org.gnome.Platform/x86_64/45
            Sdk: org.gnome.Sdk/x86_64/45

         Commit: 110f79f4f225dcb262daa49fbbf6c37dc860a5abb38f191b8e910d6478a8494a
         Parent: 941896414262f627d345de89571af0d837ec7d7797a7bdb7c2eb6e8da76fb351
        Subject: Export io.github.starnight.gtkdemo
           Date: 2023-11-04 14:07:59 +0000
   ```

## Execute

Run flatpak **io.github.starnight.gtkdemo** application:
`flatpak run io.github.starnight.gtkdemo`

If you want to remove it: `flatpak uninstall io.github.starnight.gtkdemo`


## Reference

* [Flatpak document](https://docs.flatpak.org/en/latest/)
* [The Meson Build System's Tutorial](https://mesonbuild.com/Tutorial.html)
