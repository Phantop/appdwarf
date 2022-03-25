appdwarf
=======
A tool to convert an AppDir or an existing [AppImage](https://appimage.org/) file,
either as a local file or from a URL, into a highly compressed portable image using
[dwarfs](https://github.com/mhx/dwarfs).

This is a small script and the bulk of the work is in the original `dwarfs` project,
so all credit deserves to go there and I can not guarantee this script will function
with out issues.

## Requirements

In order to create the images, you will need:

- [dwarfs](https://github.com/mhx/dwarfs), specifically the `dwarfs` and `mkdwarfs` utilities.
    - This may in turn require further dependencies, and specifically relies on the presence of FUSE for mounting images.

If you only wish to run an existing image, only `dwarfs` is needed in PATH.

## How to create an appdwarf

For your own programs, simply create an AppImage-style AppDir and run `appdwarf {directory}`. 
You can also invoke `appdwarf -a {appimage}` to convert an apimage. 
I suggest checking the help (listed via `appdwarf --help`) for other options.

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

## Known Issues

- Some images may not unmount properly under the default, combined mounting scheme due
to the inability to use lazy unmounting and some programs still making use of the filesystem
when `fusermount -u` is run.
    - Can be worked around with the separate header at the cost of memory/CPU usage.
