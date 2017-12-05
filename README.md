# AsynInterposeEcho

This is an interpose layer for asyn octet drivers.
It adds the feature to wait after every single character
written to the device until the device echos it back.
Some very crappy devices need this.

## Usage

In the startup script, after loading the `asynInterposeEcho` driver and
setting up an asyn octet port,
call `asynInterposeEcho` to add this interpose layer to an existing
asyn octet port/address.

```
asynInterposeEcho port, address
```

## Example
```
require asynInterposeEcho
drvAsynSerialPortConfigure "device", "/dev/ttyS0"
asynInterposeEcho "device"
```
