appdwarf
=======
A tool to convert an AppDir or an existing [AppImage](https://appimage.org/) file,
either as a local file or from a URL, into a highly compressed portable image using
[dwarfs](https://github.com/mhx/dwarfs).

This is a small script and the bulk of the work is in the original `dwarfs` project,
so all credit deserves to go there. This script has not been extensively tested so I
cannot guarantee it will function without issue.

## Requirements

In order to create the images, you will need:

- [dwarfs](https://github.com/mhx/dwarfs), specifically `mkdwarfs`
    - This may in turn require further dependencies, and specifically relies on the presence of FUSE for mounting images.
    - `dwarfsck` and `dwarfsextract` also allow for converting existing dwarfs images and updating the header of existing appdwarfs
- squashfs-tools for AppImage conversion
- `zstd` for creating or running `zzexe` files

If you only wish to run an existing appdwarf, only `dwarfs` is needed in PATH.

## How to create an appdwarf

`appdwarf` can take both AppImage files and extracted AppDirs as input. If a file
or folder is not found, `appdwarf` will also accept direct URLs to AppImages, links
or names to GitHub repos with AppImages in their releases page, or names of programs
that meet the GitHub criteria on AppImageHub. Any files that are found but are not
AppImages will be compressed using `zzexe`.

The apps folder contains other scripts for specific programs that will download all
necessary files and create a resulting appdwarf in the `bin` subfolder.

## `zzexe`

`zzexe` is a small tool similar to `gzexe` that instead uses zstd to compress single applications.
I've included it because it has a similar goal to `appdwarf` on the whole, just on a smaller scale.

I wrote it in part because I felt that `gzexe` was overly complicated, as I had been 
using lightly modified version of it that replaces `gzip` with `zstd`, and to add a
couple additional features:

- supports adding in a prefix command to the file using the `-p` option
    - e.g. `zzexe -p wine some.exe` will generate a compressed file that will then run the exe with wine
- automatically appends the extension of the source file to the temporary file
created when ran since some programs care about that, such as an emulator only
running games of an expected file extension.

*As of June 2022, `zzexe` has been integrated into the main `appdwarf` script. 
I have implemented a heuristic that should automatically detect regular files and
run `zzexe` on them, however you can directly invoke it with the `-z` option.*
