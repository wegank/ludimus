# Ludimus

[![Build Status](https://travis-ci.org/wegank/ludimus.svg?branch=master)](https://travis-ci.org/wegank/ludimus)

Ludimus is a cross-platform AirPlay mirroring server, based on [RPiPlay](https://github.com/FD-/RPiPlay) and [UxPlay](https://github.com/antimof/UxPlay).

Ludimus runs on:

- macOS 10.15, with Homebrew
- Ubuntu 20.04
- Windows 10 version 2004, with MSYS2

## Building

See the [wiki](https://github.com/wegank/ludimus/wiki) for more details.

## Usage

Run the executable and Ludimus will appear in the network.

The following options are implemented:

- **-n name**: Specify the network name of the AirPlay server.
- **-a**: Turn off audio and show video only.
- **-d**: Enables debug logging. Will lead to choppy playback due to heavy console output.
- **-v/-h**: Displays short help and version information.

## Credits

Ludimus is heavily inspired by this [pull request](https://github.com/FD-/RPiPlay/pull/146) to the upstream repository RPiPlay, allowing generic Linux builds.

As both repositories share the same codebase, I would suggest that anyone wishing to contribute to Ludimus make a pull request directly to RPiPlay.

## License

Ludimus is licensed under the GNU General Public License v3.0.
