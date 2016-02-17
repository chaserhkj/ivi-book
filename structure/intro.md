# Stack structure

An instrument interfacing hardware and software stack involves a number of
standards to work. Tools and libraries act as different implementations
of these standards.

* Hardware standards
    * [General Purpose Interface Bus (GPIB)](http://www.ni.com/white-paper/3388/en/)
    * Universal Serial Bus (USB)
        * [USB Test and Measurement Class (USBTMC)](http://ivifoundation.org/downloads/Class%20Specifications/Ivi-6%202_USBTMC_2010-03-23.pdf)
    * LAN/Ethernet
        * [LAN eXtensions for Instrumentation](http://www.lxistandard.org/about/vxi-11-and-lxi.aspx)
        * [VXI-11 Protocol](http://vxibus.org/specifications.html)
* Software standards
    * [Virtual Instrument Software Architecture (VISA)](http://ivifoundation.org/specifications/default.aspx)
        * Common implementations:
            * [NI-VISA](https://www.ni.com/visa/) by National Instruments
            * [pyVISA](https://pyvisa.readthedocs.org/) as part of the python
            stack we use
    * [Interchangeable Virtual Instruments (IVI)](http://ivifoundation.org/specifications/default.aspx)
        * Common implementations:
            * [NI-IDL](http://www.ni.com/ivi/idl.htm) IVI Driver Library by
            National Instruments
            * [python-ivi](https://github.com/python-ivi/python-ivi) as part of
            the python stack we use

Most of the common-used instrument standards are maintained by [the IVI
foundation](http://www.ivifoundation.org/) and their specification collection
could be accessed [here](http://ivifoundation.org/specifications/default.aspx).
