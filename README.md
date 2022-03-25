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

The apps folder contains other scripts for specific programs that will download all necessary files and create a resulting appdwarf in the same folder.

## Known Issues

- Some images may not unmount properly under the default, combined mounting scheme due
to the inability to use lazy unmounting and some programs still making use of the filesystem
when `fusermount -u` is run.
    - Can be worked around with the separate header at the cost of memory/CPU usage.
