<<<<<<< HEAD
# wine-portable-executable
Wine builds packed into a portable executables
=======
## Description

These scripts automatically fetch the latest version of their respective program and compress them into a portable image using [dwarfs](https://github.com/mhx/dwarfs) in a similar format to an [AppImage.](https://appimage.org/)

## Requirements

In order to create the images, you will need:

- [dwarfs](https://github.com/mhx/dwarfs), specifically the `dwarfs` and `mkdwarfs` utilities (`dwarfs2` works, but you must either edit the script or link `dwarfs` to it)

- My `appdwarf` script from [here](https://github.com/Phantop/dotfiles/blob/main/.local/bin/appdwarf)

If you only wish to run an existing image, only `dwarfs` (or `dwarfs2`) is needed.

## How to create portable executables

Use the corresponding script for the desired program. 

This script will use ready-to-use binaries to create portable executables.

## Notes

Keep in mind that this project is new and it has not been thoroughly tested. Please report any problems you find.

## Credits

[wine-portable-executable](https://github.com/Kron4ek/wine-portable-executable) and [Wine-Builds](https://github.com/Kron4ek/Wine-Builds) by [Kron4ek](https://github.com/Kron4ek)

[dwarfs](https://github.com/mhx/dwarfs) by [mhx](https://github.com/mhx)

Java builds from [AdoptOpenJDK](https://adoptopenjdk.net/)
>>>>>>> fe54f14 (dwarfs, latest builds, add java)
