# Linux Installation

## Python

Most Linux distributions may come along with `python` and `pip` already
installed, if not, install them first:

Arch Linux:

    # pacman -S python2-pip

Debian/Ubuntu:

    # apt-get install python-pip

CentOS/Fedora:

    # yum install python-pip

## PyVISA

If you wish to use `PyVISA` to perform command-based instrument programming, get
`PyVISA` installed first:

    # pip install pyvisa

If you don't wish to install the stack system-wide, but only to install it in
the local user scope, `--user` flag could be appended to `install` subcommand
and root permission could be omitted.

    $ pip install --user pyvisa

All python package installation follow the same guideline.

Now `PyVISA` needs a back-end to work, which you could have an option.

### NI-VISA

You could choose to install VISA library provided by National Instruments as the
back-end of PyVISA. NI-VISA library for Linux is mainly packaged for RPM-based
Linux distributions and installation on these distributions such as CentOS,
scientific Linux or Fedora would be easy.

For installation guidelines of NI-VISA, please refer to the National Instruments
[website](http://www.ni.com/download/ni-visa-5.4/4234/en/).

### pyvisa-py

`PyVISA` provides a pure python back-end which is free and open source. One who
is not able or convenient enough to install `NI-VISA` should turn to this choice.

    # pip install pyvisa-py

`pyvisa-py` relies on a number of python packages for interface communication.


#### pyusb

For connecting to devices through USB, `pyusb` must be installed.

Install `libusb` first for `pyusb` to work

Arch linux:

    # pacman -S libusb

Debian/Ubuntu:

    # apt-get install libusb

CentOS/Fedora:

    # yum install libusb

And then install `pyusb`

    # pip install pyusb

#### python-gpib

For connecting to devices through GPIB, `python-gpib` must be installed.

This module is part of the `linux-gpib` driver, it also requires the kernel
driver to function, which could be installed through source code. Detailed
installation guide could be found at [project
site](http://linux-gpib.sourceforge.net/).

For **Arch Linux** users, this could be installed through AUR:

    $ yaourt -S python2-gpib

#### pyserial

For connecting to devices through serial ports, `pyserial` must be installed.

    # pip install pyserial

## python-ivi

If you wish to use `python-ivi` to achieve object-oriented programming level
instrument control, install `python-ivi` package first.

    # pip install python-ivi

`python-ivi` relies on multiple communication library to talk to different
instrument interfaces.

### python-vxi11

For communication using VXI-11 protocol over Ethernet/LAN interface, `python-ivi`
package requires `python-vxi11` to run.

    # pip install python-vxi11

### python-usbtmc

For communication using USBTMC protocol over USB interface, `python-usbtmc` must
be installed.

    # pip install python-usbtmc

### python-gpib

For communication over GPIB interface, `python-gpib` and corresponding Linux
kernel space driver `linux-gpib` must be installed.

Please follow the previous metioned guidelines to install `linux-gpib` and its
python bindings.
