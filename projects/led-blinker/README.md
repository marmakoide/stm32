# led-blinker

This is the STM32's Hello World : blinking the on-board led. It shows how 
to set a pin on and off.

 * Compile with the following command : `make`
 * Upload to the STM32 with the following command : `make upload`
 * Clean-up with the following command : `make clean`

If you peek into the Makefile, you'll see that the build process is not as 
straight-forward, the linking step requires custom script.
