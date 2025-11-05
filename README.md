# ee186_all
new repo for the rest of labs for Stanford's ee186 course (please never make me do this again (i'm kidding this class is fun (but i've never a datasheet this deeply ever)))!

## LAB 4

**1. What are the different bit resolutions can you set the ADC? What is the maximum sampling rate at each of these resolutions? Where did you find this information in the datasheet?**
A: 12, 10, 8 or 6-bit configurable resolution according to ADC main feature section. Maximum sample rate for each resolution is 8000 hz, 9230 hz, 10909 hz, and 13333 hz respectively. 

**2. Why do you need a voltage divider circuit? What would happen if the photodiode is directly connected to the board?**
A: Without the voltage divider, all of the voltage will drop across the one resistor, not really indicating the change of resistance across the photodiode (or whatever resistor we are using). The photodiode would just have 3v3 drop constantly.

**3. If B = 9, what is Vout? Express your answer in terms of Vref . Use the DAC mode that provides the best resolution available on your MCU (refer to the data sheet).**
A: v_out = 9/2^(12) * V_ref= 0.002197265625 * V_ref

**4. How does the sampling rate of the DAC affect the quality of the output waveform? What are the differences in sound perception between sine, square, and sawtooth waves? Why do we need a capacitor in the signal path when sending an audio signal to a speaker or earphones?**
A: The DAC sampling rate impacts how smooth the sound wave will be (smaller sampling rate means choppier audio). Sine waves sound like normal notes, square waves a sharp, and sawtoths are loud and buzzy. A capacitor allows us to filter the square and sawtooth waves to have a smooth sine wave equivalent that emulates a normal sound wave. 

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