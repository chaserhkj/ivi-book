# Windows installation

Windows users are recommended to install a binary distribution of python stack
before install any packages that relates to instrument control.

A binary distribution that has the `scipy` stack pre-installed is strongly
recommended. Various instrument control packages relies on `scipy` stack to
perform math operations. Without a binary distribution, users may need to build
`scipy` stack themselves.

The following links are a recommended list of `scipy` binary distributions.

* [Anaconda](http://continuum.io/downloads)
* [Enthought Canopy](http://www.enthought.com/products/canopy/)
* [Python(x, y)](http://python-xy.github.io/)
* [WinPython](http://winpython.github.io/)
* [Pyzo](http://www.pyzo.org/)

This list is originally from `scipy`'s official
[website](https://scipy.org/install.html), and may be updated afterwards,
please refer to the site for most updated versions.

Please choose from the above list according to your preference, and install the
distribution following the official guidelines it provides.

## Installation of packages

After installing your chosen distribution, following the official guidelines,
you should gain your access to your `pip` command within your installed
distribution.

Just follow all the installation guidelines in the [Linux installation
section](./linux.md) using `pip` to installed your preferred packages of
instrument control.

**NOTE: `linux-gpib` and `python-gpib` are only for linux platforms, for those
who wish to use GPIB interface on Windows platform, your only option is to use
`PyVISA` with `NI-VISA`, together with another proper GPIB drvier for your GPIB
controller device.**
