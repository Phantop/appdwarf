appdwarf
=======
These scripts automatically fetch the latest version of their respective program and compress them into a portable image using [dwarfs](https://github.com/mhx/dwarfs) in a similar format to an [AppImage.](https://appimage.org/)

The titular `appdwarf` utility supports both converting an AppDir or an existing AppImage file, either as a local file or from a URL, and is used similarly to how 'appimagetool' is.

## Requirements

In order to create the images, you will need:

- [dwarfs](https://github.com/mhx/dwarfs), specifically the `dwarfs` and `mkdwarfs` utilities (`dwarfs2` works, but you must either edit the script or link `dwarfs` to it)


If you only wish to run an existing image, only `dwarfs` (or `dwarfs2`) is needed.

## How to create portable executables

For your own programs, simply create an AppImage-style AppDir and run `appdwarf {directory}` or use one of the additional options (listed via `appdwarf --help`) to convert an existing AppImage to appdwarf.

The other scripts for specific programs will download all necessary files and create a resulting appdwarf in the same folder.

## Notes

Keep in mind that this project is new and it has not been thoroughly tested. Please report any problems you find.

## Credits

[wine-portable-executable](https://github.com/Kron4ek/wine-portable-executable) and [Wine-Builds](https://github.com/Kron4ek/Wine-Builds) by [Kron4ek](https://github.com/Kron4ek)

[dwarfs](https://github.com/mhx/dwarfs) by [mhx](https://github.com/mhx)

Java builds from [AdoptOpenJDK](https://adoptopenjdk.net/)
