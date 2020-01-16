##1/16/2020
	-Went over loops: while, for, goto, do..while
	-Part number is mbed LPC1768 
	
#Active-high/low logic? LED?
	-The LED is on when put out logic high
	
	-Newer LEDs like blue, have forward voltage and these LEDs in active low can be connected to another vcc that is not technically in the chip
	-Easier to get a positive power rail

#main.cpp

	# include "mbed.h"

	DigitalOut myled(p20);
	DigitalOut otherled(LED4);


int main() {

	while(1) {

		myled = 1;
		otherled = 0;
		wait(0.5);
		myled = 0;
		otherled = 1;
		wait(0.5);
		}

#Chips

	-74LS00 - NAND gate
		- sink 4 mA (current going into the chip) | Driving low
		- source 200mA  (current going out of the chip) | Driving high
		
#Code
	
	# include "mbed.h"

	DigitalOut myled(LED1);
	DigitalIn sw(p22);

int isPressed(void)
{
return sw == 1;
}


int main() {

	while(1){

		if (isPressed()){
			myled = !myled;  #50 percent chance of not working
			wait(0.5); #this gives half a second delay

		}
	}


#DigitalIn class

	DigitalIn(pin)
	DigitalIn(pin, resistor mode) <- could be pull up, down, or none. #if not chosen, it defaults to pull down
	int read() 
	operator(int)  #shorthand for read()
	mode(resistor mode) #lets us do from the constructor, select what we want it to do








