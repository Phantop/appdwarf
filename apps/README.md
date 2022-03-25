# Apps

This directory contains various scripts I've put together to quickly and easily create
images of various large and/or popular programs. I give no guarantee that they will
work correctly or as desired; these have been put together largely for my own usage.

These scripts are all targeted for using on x86_64 Linux systems with GLIBC.

## Scripts

Script | Function | Source
--- | --- | ---
`appimage ` | Can fetch and convert AppImages by name from AppImageHub if the source repo is hosted on GitHub and linked to | <https://appimage.github.io>
`github   ` | Can be given a GitHub URL or repo in the form `user/repo` and will find and convert the latest AppImage release | <https://github.com>
`mkchrome ` | Latest official Chromium build | <https://download-chromium.appspot.com>
`mkgo     ` | Latest official Go release | <https://go.dev>
`mkjava   ` | Accepts an argument for Java version and obtains that build from Adoptium | <https://adoptium.net>
`mknode   ` | Latest official NodeJS release | <https://nodejs.org>
`mkproton ` | GloriousEggroll Proton Builds | <https://github.com/GloriousEggroll/proton-ge-custom>
`mkpypy   ` | Latest PyPy3 release | <https://www.pypy.org>
`mkrust   ` | Latest Rust nightly | <https://rust-lang.org>
`mktex    ` | Minimal/custom TeX Live image | <https://ctan.org>
`mkwine   ` | Latest `wine-staging-tkg` release | <https://github.com/Kron4ek/Wine-Builds>
`rustsolus` | Latest Rust stable from the Solus repos (requires `eopkg` and may not work on other distros) | <https://getsol.us>
`ungoogled` | Latest submitted `ungoogled-chromium` binary release | <https://ungoogled-software.github.io/ungoogled-chromium-binaries>
