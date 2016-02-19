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
