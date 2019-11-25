Intan RHD2000 Electroplating Interface Software (64c/128c)
----------------------------------------------------------

This repository contains *modified* code for electroplating using the
[Intan RHD2000 Electroplating System](http://intantech.com/RHD2000_electroplating_board.html).
The software in this repository has been designed to work with our custom 64 channel
recording & plating amplifier boards (schematics will be published soon), but should
also still work with the existing 128 channel amplifier boards that can be ordered
directly from Intan Technologies LLC.

In order to run the software provided with this repository, you will need
the operating system specific Opal Kelly library files. These have been moved to a
[separate repository](https://github.com/bothlab/intan-okfrontpanel) so they can be shared
between multiple projects that connect to Intan devices which use Opal Kelly FPGA integration modules.

## How to install

On Debian/Ubuntu **Linux**, just download the ready-made .deb packages from the Github release and install them.
You should then be able to launch the electroplating software from the application menu.

Alternatively, compile from source (works on any Linux distribution as long as the required dependencies
are installed):
```bash
$ sudo apt install build-essential git cmake meson ninja-build qt5-default
$ git clone https://github.com/bothlab/intan-okfrontpanel
$ cd intan-okfrontpanel && mkdir build && cd build
$ meson .. && sudo ninja install
$ cd ../..
$ git clone https://github.com/bothlab/rhd2000electroplating.git
$ cd rhd2000electroplating && mkdir build && cd build
$ cmake -DCMAKE_BUILDTYPE=RelWithDebInfo ..
$ make && sudo make install
```
On **Windows**, download and install the USB drivers from the Intan Technologies website before
connecting the RHD2000 electroplating board to a computer. You can then use the prebuilt Windows
binary from the [Github release](https://github.com/bothlab/rhd2000electroplating/releases).
