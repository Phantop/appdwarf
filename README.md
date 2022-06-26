appdwarf
=======
A tool to convert an AppDir or an existing [AppImage](https://appimage.org/) file,
either as a local file or from a URL, into a highly compressed portable image using
[dwarfs](https://github.com/mhx/dwarfs).

This is a small script and the bulk of the work is in the original `dwarfs` project,
so all credit deserves to go there. It has not been extensively tested so I cannot
guarantee it will function without issue.

## Requirements

In order to create the images, you will need:

- [dwarfs](https://github.com/mhx/dwarfs), specifically the `dwarfs` and `mkdwarfs` utilities.
    - This may in turn require further dependencies, and specifically relies on the presence of FUSE for mounting images.

If you only wish to run an existing image, only `dwarfs` is needed in PATH.

## How to create an appdwarf

`appdwarf` can take both AppImage files and extracted AppDirs as input. If a file
or folder is not found, `appdwarf` will also accept direct URLs to AppImages, links
or names to GitHub repos with AppImages in their releases page, or names of programs
that meet the GitHub criteria on AppImageHub. Any files that are found but are not
AppImages will be compressed using `zzexe`.

The apps folder contains other scripts for specific programs that will download all
necessary files and create a resulting appdwarf in the same folder.

## `zzexe`

`zzexe` is a small tool similar to `gzexe` that instead uses zstd to compress single applications.
I've included it because it has a similar goal to `appdwarf` on the whole, just on a smaller scale.

I wrote it in part because I felt that `gzexe` was overly complicated, as I used to 
just use a lightly modified version of it that replaces `gzip` with `zstd`,
and to add a couple additional features. 

It supports adding in a prefix command to the file using the `-p` options e.g.
`zzexe -p wine some.exe` will generate a compressed file that will then run the exe.

It also automatically appends the extension of the source file to the temporary file
created when ran since some programs care about that, such as an emulator only
running games of an expected file extension.

`zzexe` requires `zstd` for both creating and running files and `moreutils` for creating them.
