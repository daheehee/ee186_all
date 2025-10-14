# ee186_all
new repo for the rest of labs for Stanford's ee186 course (please never make me do this again)!

## LAB 2
**1. Explain how external interrupts work.**
A: interrupts flag the signal to let the main code know that something happened to trigger the isr (interupt service routine). Once the system stacks all the necessary memory to the main stack, the ISR runs and then unstacks after it is finished. If the pending flag is still active, the ISR will run again after the first time finishes.

**2. Explain how timer interrupt works.** 
A: Timer interrupts utilize an on-board oscillators that counts to certain number of clock cycles. 
When that number is reached, an ISR is triggered. Unlike other interrupts, this does not need 
and external trigger (like a push of a button or a voice to trigger a sensor). 

**3. Calculation provided as photo in the lab2 folder!**