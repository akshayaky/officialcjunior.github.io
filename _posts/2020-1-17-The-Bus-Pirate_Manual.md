# The Bus Pirate Mannual

This mannual covers the essential stuff that you don't want to miss while using a [Bus Pirate](http://dangerousprototypes.com/docs/Bus_Pirate).

# Flashing the firmware

After connecting the Bus Pirate, and cloning the [repository](https://github.com/BusPirate/Bus_Pirate), simply navigate to the firmware folder of the version ofthe Bus Pirate you own.

You can flash the firmware using the `pirate-loader`.
It requires only the firmware hex file and the device name as arguments.

So, if you are running Linux, you can flash it, just by running 
`./pirate-loader_lnx --dev=/dev/ttyUSB --hex=busPirate.x`

Keep in mind that you have to connect the PGC and PGD pins of the Bus Pirate using a jumper cable to trigger the Bus Pirate bootloader. This is will make the MODE LED turn on.

## Interfacing with the Bus Pirate

The Bus Pirate uses a baud rate of 115200. Using GNU Screen, we can talk to the device just by running:

`sudo screen /dev/ttyUSBO 115200`

You'll enter a shell with prompt `<HiZ>` 

## UART

To, sniff data being sent using the UART protocol, choose 3, from the mode menu.
Then, you'll be asked to set the UART mode, with port speed, data bits per frame, polarity, stop bits and output type.

Just as you thought, connect MOSI of the device to the RX and MISO to TX along with a commmon ground.

Opening UART using the `[` command won't work all the time, as the the Bus Pirate Hardware only has a four-byte buffer, causing a Buffer overun if the data is over four bytes.

So, use the macro (2), The Live UART monitor to view the data.

## I2C

To get started, connect the MOSI pin of the Buspirate to the SDA pin and the Clock pin to the SCL pin of the ciruit.

To set up the Bus Pirate to read data being sent through I2C, choose 4 from the Mode Menu.

Set the speed and run the macro (2) to see the data.

It is also possible to find the addresses of all the I2C chips on the network using the macro (1), as each I2C chip addressis a 7 bit address and there can only be 128 unique devices on the same wire.

## SPI

Connect MOSI and MISO of the Bus Pirate to the MOSI and MISO of the circuit. You'll also need to connect pins for the Chip Select and the Clock Signal. Don't forget about grounding it commonly.

Choose the SPI mode from the Mode menu and go with the default settings for everything except the speed, unless you're really sure about what you're doing.

