# Ludimus

This project is an early-stage prototype of an AirPlay mirroring server for macOS, based on [RPiPlay](https://github.com/FD-/RPiPlay) and [UxPlay](https://github.com/antimof/UxPlay).

Tested on macOS 10.15.6.

## Prerequisites

### macOS

```bash
brew install cmake openssl gstreamer gst-plugins-base gst-plugins-good gst-plugins-bad gst-plugins-ugly gst-libav
export LDFLAGS="-L/usr/local/opt/openssl@1.1/lib"
export CPPFLAGS="-I/usr/local/opt/openssl@1.1/include"
export PKG_CONFIG_PATH="/usr/local/opt/openssl@1.1/lib/pkgconfig"
```

### Ubuntu

```bash
sudo apt install git cmake libssl-dev libavahi-compat-libdnssd-dev libgstreamer1.0-dev libgstreamer-plugins-base1.0-dev gstreamer1.0-plugins-base gstreamer1.0-plugins-good gstreamer1.0-plugins-bad gstreamer1.0-plugins-ugly gstreamer1.0-libav gstreamer1.0-vaapi
sudo apt install gstreamer1.0-doc gstreamer1.0-tools gstreamer1.0-x gstreamer1.0-alsa gstreamer1.0-gl gstreamer1.0-gtk3 gstreamer1.0-qt5 gstreamer1.0-pulseaudio
```

## Building

```bash
mkdir build
cd build
cmake ..
make
```
