# LIS2DW12
Arduino library to support the LIS2DW12 3D accelerometer

## API

This sensor uses I2C or SPI to communicate.
For I2C it is then required to create a TwoWire interface before accessing to the sensors:  

    dev_i2c = new TwoWire(I2C_SDA, I2C_SCL);  
    dev_i2c->begin();

For SPI it is then required to create a SPI interface before accessing to the sensors:  

    dev_spi = new SPIClass(SPI_MOSI, SPI_MISO, SPI_SCK);  
    dev_spi->begin();

An instance can be created and enbaled when the I2C bus is used following the procedure below:  

    Accelero = new LIS2DW12Sensor(dev_i2c);  
    Accelero->Enable();

An instance can be created and enbaled when the SPI bus is used following the procedure below:  

    Accelero = new LIS2DW12Sensor(dev_spi, CS_PIN);  
    Accelero->Enable();

The access to the sensor values is done as explained below:  

  Read accelerometer.  

    Accelero->GetAxes(&accelerometer);  

## Documentation

You can find the source files at  
https://github.com/stm32duino/LIS2DW12

The LIS2DW12 datasheet is available at  
https://www.st.com/content/st_com/en/products/mems-and-sensors/accelerometers/lis2dw12.html
