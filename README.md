# REC360 Gyro Calibration

<h4>Requirements:</h4>
- Raspberry Pi GCC Cross-Compiler Toolchains, see https://github.com/abhiTronix/raspberry-pi-cross-compilers

- Version <b>8.3.0</b>, Target OS <b>Buster</b>, Target Platform <b>Pi 1/Zero</b> 

## To compile on a Raspberry Pi (1 or 2 or 3)

1. install the bcm2835 library, see http://www.airspayce.com/mikem/bcm2835/index.html
2. enable i2c on your RPi, see https://learn.adafruit.com/adafruits-raspberry-pi-lesson-4-gpio-setup/configuring-i2c
3. connect your i2c devices
4. then from bash
    `$ gcc -o IMU_zero ./IMU_zero.cpp \`
    `    -I ../../I2Cdev ../../I2Cdev/I2Cdev.cpp \`
    `    -I ../. ../MPU6050.cpp \`
    `    -l bcm2835 -l m`

    `$ PATH_I2CDEVLIB=~/i2cdevlib/`

    `$ gcc -o IMU_zero ${PATH_I2CDEVLIB}RaspberryPi_bcm2835/MPU6050 examples/IMU_zero.cpp \`
        `-I ${PATH_I2CDEVLIB}RaspberryPi_bcm2835/I2Cdev ${PATH_I2CDEVLIB}RaspberryPi_bcm2835/I2Cdev/I2Cdev.cpp \`
        `-I ${PATH_I2CDEVLIB}RaspberryPi_bcm2835/MPU6050/ ${PATH_I2CDEVLIB}RaspberryPi_bcm2835/MPU6050 MPU6050.cpp \ -l bcm2835 -l m`

    `$ sudo ./IMU_zero`

<hr />

***Note: additional details about this project can be found at https://www.i2cdevlib.com***
