# mpv-macos

mpv-macos is a macOS packaging for the latest stable release of [mpv](https://github.com/mpv-player/mpv).

## Downloads

Built application can be downloaded from the [Releases](https://github.com/pashynskykh/mpv-macos/releases).

## Installation

1. Mount the DMG and drag and drop the app into your Applications directory.
2. Remove the "quarantine" attribute from the app:
   ```bash
   xattr -d com.apple.quarantine /Applications/mpv.app
   ```

## FAQ

### Can I trust your builds?

My mpv packages are built directly from source and I don't make any changes or even store the source code in this repository.

Also, you don't have to trust me, since you can check the build.yml file in this repository and make sure that it is indeed built from the original source code of the latest stable mpv release, without any modifications.

### Why I can't open the app after installation?

If you've forgotten to remove the "quarantine" attribute, you'll receive the following message from macOS, which will prevent you from opening the application:
> Apple could not verify "mpv.app" is free of malware that may harm your Mac or compromise your privacy.

This happens because I do not notarize the macOS version of the mpv: I don't have a paid Apple Developer license and I don't want to support this signing mechanism that is put behind a paywall without providing significant gains.

### How do I use mpv on MacOS from the Terminal?

There are two ways to make `mpv` available on the terminal:

1. Create an alias in your `.zshrc`, `.bashrc`, or `config.fish` file, depending on the shell you are using. For example, let's add an alias for ZSH by adding the following line to `~/.zshrc`:
   ```bash
   alias mpv="/Applications/mpv.app/Contents/MacOS/mpv"
   ```
   After that, you'll need to reopen the terminal and the `mpv` command will be available to you.
2. Create a soft link to one of your paths in `$PATH`. For example:
   ```bash
   ln -s /Applications/mpv.app/Contents/MacOS/mpv /usr/local/bin/mpv
   ```

### There's a new version of mpv out. When will you update?

As soon as I manage to get some time away from work.

## License

See [LICENSE](LICENSE).
