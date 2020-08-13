# Ludimus [![Build Status](https://travis-ci.org/wegank/ludimus.svg?branch=master)](https://travis-ci.org/wegank/ludimus)

Ludimus is an early-stage prototype of a cross-platform AirPlay mirroring  
server, based on [RPiPlay](https://github.com/FD-/RPiPlay) and [UxPlay](https://github.com/antimof/UxPlay).

Ludimus runs on:

- macOS 10.15, with Homebrew
- Ubuntu 20.04
- Windows 10 version 2004, with MSYS2

## Dependencies

### macOS

```bash
brew install cmake openssl gstreamer gst-plugins-base gst-plugins-good gst-plugins-bad gst-plugins-ugly gst-libav
```

### Ubuntu

```bash
sudo apt install git cmake libssl-dev libavahi-compat-libdnssd-dev libgstreamer1.0-dev libgstreamer-plugins-base1.0-dev gstreamer1.0-plugins-base gstreamer1.0-plugins-good gstreamer1.0-plugins-bad gstreamer1.0-plugins-ugly gstreamer1.0-libav gstreamer1.0-vaapi
sudo apt install gstreamer1.0-doc gstreamer1.0-tools gstreamer1.0-x gstreamer1.0-alsa gstreamer1.0-gl gstreamer1.0-gtk3 gstreamer1.0-qt5 gstreamer1.0-pulseaudio
```

### Windows

```bash
pacman -S mingw-w64-x86_64-toolchain git mingw-w64-x86_64-cmake mingw-w64-x86_64-openssl mingw-w64-x86_64-gstreamer mingw-w64-x86_64-gst-plugins-base mingw-w64-x86_64-gst-plugins-good mingw-w64-x86_64-gst-plugins-bad mingw-w64-x86_64-gst-plugins-ugly mingw-w64-x86_64-gst-libav
```

## Building

### macOS

```bash
export LDFLAGS="-L/usr/local/opt/openssl@1.1/lib"
export CPPFLAGS="-I/usr/local/opt/openssl@1.1/include"
export PKG_CONFIG_PATH="/usr/local/opt/openssl@1.1/lib/pkgconfig"

mkdir build
cd build
cmake ..
make
```

### Ubuntu

```bash
mkdir build
cd build
cmake ..
make
```

### Windows

```bash
mkdir build
cd build
cmake .. -G "MinGW Makefiles"
mingw32-make
```
