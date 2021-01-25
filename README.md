# LIS2DW12
Arduino library to support the LIS2DW12 3D accelerometer

## API

This sensor uses I2C or SPI to communicate.
For I2C it is then required to create a TwoWire interface before accessing to the sensors:  

    TwoWire dev_i2c(I2C_SDA, I2C_SCL);  
    dev_i2c.begin();

For SPI it is then required to create a SPI interface before accessing to the sensors:  

    SPIClass dev_spi(SPI_MOSI, SPI_MISO, SPI_SCK);  
    dev_spi.begin();

An instance can be created and enabled when the I2C bus is used following the procedure below:  

    LIS2DW12Sensor Accelero(&dev_i2c);
    Accelero.begin();
    Accelero.Enable_X();

An instance can be created and enabled when the SPI bus is used following the procedure below:  

    LIS2DW12Sensor Accelero(&dev_spi, CS_PIN);  
    Accelero.begin();
    Accelero.Enable_X();

The access to the sensor values is done as explained below:  

  Read accelerometer.  

    int32_t accelerometer[3];
    Accelero.Get_X_Axes(accelerometer);  

## Documentation

You can find the source files at  
https://github.com/stm32duino/LIS2DW12

The LIS2DW12 datasheet is available at  
https://www.st.com/content/st_com/en/products/mems-and-sensors/accelerometers/lis2dw12.html
