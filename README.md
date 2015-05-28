SoftwareSPI
-----------

This is a simple library to simplify bit-banging SPI on an Arduino. It accepts any arduino pins and uses only digitalWrites and digitalReads to handle the data.

First include the library:
    #include <SoftwareSPI.h>

Then initialize it with the correct pins:
    SoftwareSPI spi(SPI_SCK,SPI_MOSI,SPI_MISO,SPI_CS);

**Note: You can use 0 for the CS pin if you don't plan on using spi.select() or spi.deselect()**

Before using it, configure the pins by calling begin:
    spi.begin();

Transfer data by using select, transfer, and deselect:
    spi.select();
    byte value = spi.transfer(5);
    spi.deselect();

