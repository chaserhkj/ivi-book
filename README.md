# Introduction to Instrument Control Using Python

This book briefly describes the hardware protocol and software interfaces that
a modern IVI-specification-compatible instrument device should offer, and gives
out guidelines about interfacing these devices with python programming language
using examples.

## Stack Structure

Modern experimental instrument devices uses **GPIB/USB/LAN** as hardware
interfaces to talk with controllers (eg. Laboratory computers), utilizing the
use of protocols such as **USBTMC** on USB interface and **VXI-11** on LAN
interface, providing a command-respond-event model of operating devices. Most of
the devices define their operating commands with compliance to the **Standard
Commands for Programmable Instrumentation (SCPI)** specifications.

Instrument vendors, software providers and open source community have built a
large number of software stacks to help interfacing with instruments, most of
these stacks are compliant to the **Virtual Instrument Software Architecture
(VISA)** standards. Implementing the **Interchangeable Virtual Instruments
(IVI)** standards, some of these stacks can even provide high abstraction at the
level of object-oriented programming.

All these protocols, standards and specifications are maintained by the IVI
foundation. This part will describe the logical structure of these hardware and
software stacks, especially on the python stack which we'll be using.

## Installation and deployment

The python stack for interfacing instruments including packages such as
**PyVISA, python-ivi, python-vxi, python-usbtmc, python-gpib**. Some of these
packages require external and native components which are platform-specific.

This part would provide guidelines for install and deploy these software stacks
to production environments on various platforms.

## Instrument control

Using the **PyVISA** and related python packages, direct command control to the
instrument devices could be implemented, which is an approach that would work
flawlessly with all compatible instruments.

Utilizing the **python-ivi** library and a proper ivi driver, object-oriented
programming level interfacing could be achieved.

This part would give concrete examples on how to interface instruments using the
two different approaches mentioned above.
