# ee186_all
new repo for the rest of labs for Stanford's ee186 course (please never make me do this again (i'm kidding this class is fun (but i've never a datasheet this deeply ever)))!

## LAB 3

**1. What is the I2C addresses of the accelerometer and magnetometer? Represent the r/w bit using b.**
A: 0b0011001 for accelerometer and 0b0011110 for magnotometer 


**2. What is the sub-address (SUB), and how does it differ from the I2C address?**
A: A sub-address is the internal addresses within the peripheral to access  certain info and execute certain tasks. This is different from the i2c address as it is used to address certain parts of the peripheral and not the whole thing.

**3. To enable acceleration data measurement, we need to configure the CTRL1 register by**
A: ob010 0000 is the address of CTRL1_REG1. it should be 0b0101_0001 to write to it and 01010111 should be written  for 100 hz operation. 

**4. To read acceleration data for the X, Y, and Z axes, what are the 8-bit sub-addresses that the transmitter would use to request the data?**
A: For high resolution, it should be 0b0101001, 0b0101011, and 0b0101101. To read to these, the MSB should be 1. 


## LAB 2
**1. Explain how external interrupts work.**
A: interrupts flag the signal to let the main code know that something happened to trigger the isr (interupt service routine). Once the system stacks all the necessary memory to the main stack, the ISR runs and then unstacks after it is finished. If the pending flag is still active, the ISR will run again after the first time finishes.

**2. Explain how timer interrupt works.** 
A: Timer interrupts utilize an on-board oscillators that counts to certain number of clock cycles. 
When that number is reached, an ISR is triggered. Unlike other interrupts, this does not need 
and external trigger (like a push of a button or a voice to trigger a sensor). 

**3. Calculation provided as photo in the lab2 folder!**