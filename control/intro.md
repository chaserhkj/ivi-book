# Instrument control

This part will use examples to describe how to achieve instrument control in
practice.

Example sections will be divided to two parts, with first part showing the
overall code listings, and the second part describing each code lines step by
step, to help understand the example codes.


## Communication protocol

As described in the structure chapter, different devices take different
specifications of communication protocols to talk to controllers. Due to the
design of the communication interfaces, devices all take a command-respond model
to work. Most devices and vendors design their device commands with compliance
to the SCPI standard. But there are indeed a few exceptions. For example,
Keithley's System SourceMeter 2600 Series SMU devices take a script syntax
called **Test Script Processor (TSP)**.

For convenience and to help understanding of the framework, the command-based
instrument control section will contain 2 examples, one featuring SCPI-based
commands and another featuring non-SCPI commands, using TSP to control
Keithley's SMU.
