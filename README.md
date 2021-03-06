# python3-smbus

## Installation

Install prerequisites:
```
apt-get install python3-dev libi2c-dev
```

Build:
```
python3 setup.py build
```

On most GNU/Linux distributions, you'll need to install the python-devel
package for the build to succeed.

To install (will also build if necessary):
```
python3 setup.py install
```

For general build/install help:
```
python3 setup.py --help-commands
```

## Frequently Answered Question:

Q: It's throwing exceptions, nothing works, what's wrong?

A1: You need write permissions to the i2c-dev devices.  Try running as root.

A2: Addresses in Linux/I2C are the most-sig 7 bits, right-justified.  E.g.
if your device uses address 0xc0 to write and 0xc1 to read, then use
	address 0x60 with this module.

A3: Some other kernel driver has claimed that I2C address.  Unload it first.

