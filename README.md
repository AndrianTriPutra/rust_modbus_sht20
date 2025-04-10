# rust_modbus_sht20

## getting_started

### permission
- connecting wiring
- connect usb485 to pc
- sudo dmesg | grep ttyUSB*
- sudo chmod a+rw /dev/ttyUSB1

#### modpoll
- cd modpoll/x86_64-linux-gnu/ (cause i use this os)
- chmod +x modpoll
- ./modpoll -t3 -b 9600 -p none -m rtu -a 1 -r 2 -c 2 /dev/ttyUSB1
```sh
with :
    -t 3          16-bit input register data type
    -b            Baudrate (e.g. 9600, 19200, ...) (19200 is default)
    -p none       No parity
    -m rtu        Modbus RTU protocol (default if SERIALPORT contains a /)
    -a            Slave address (1-247 for serial, 0-255 for TCP, 1 is default)
    -r            Start reference (1-65536, 100 is default)
    -c            Number of values to read (1-125, 1 is default), optional for writing (use -c 1 to force FC5 or FC6)
```
## run code
- cargo clean
- cargo build
- cargo run 

