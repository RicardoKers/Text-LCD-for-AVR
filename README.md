# Text LCD display library for AVR Microcontrollers
A small library for use of text LCD in 4 bit mode on AVR microcontrollers

## How to use the library:
To configure the library, select the appropriate pins and ports on the first lines of code in the TextLCD.h file, depending on the display connections in your circuit. Also define the number of columns of your display.

## Here's an example:
To connect the display to the following pins,
```
LCD data 4 - AVR PB2
LCD data 5 - AVR PB3
LCD data 6 - AVR PB4
LCD data 7 - AVR PB5
LCD E - AVR PB1
LCD RS - AVR PB0
LCD RW - GND
```
The textLCD.h file should look like this.
```
// data pin 4 from LCD
#define LCD_DATA_PORT4_H PORTB|=0b00000100
#define LCD_DATA_PORT4_L PORTB&=~0b00000100
#define LCD_DATA_DIRECTION4 DDRB|=0b00000100

// data pin 5 from LCD
#define LCD_DATA_PORT5_H PORTB|=0b00001000
#define LCD_DATA_PORT5_L PORTB&=~0b00001000
#define LCD_DATA_DIRECTION5 DDRB|=0b00001000

// data pin 6 from LCD
#define LCD_DATA_PORT6_H PORTB|=0b00010000
#define LCD_DATA_PORT6_L PORTB&=~0b00010000
#define LCD_DATA_DIRECTION6 DDRB|=0b00010000

// data pin 7 from LCD
#define LCD_DATA_PORT7_H PORTB|=0b00100000
#define LCD_DATA_PORT7_L PORTB&=~0b00100000
#define LCD_DATA_DIRECTION7 DDRB|=0b00100000

// E pin from LCD
#define LCD_E_H PORTB|=0b00000010
#define LCD_E_L PORTB&=~0b00000010
#define LCD_E_DIRECTION DDRB|=0b00000010

// RS pin from LCD
#define LCD_RS_H PORTB|=0b00000001
#define LCD_RS_L PORTB&=~0b00000001
#define LCD_RS_DIRECTION DDRB|=0b00000001

// Number of LCD columns
#define LCD_columns 20
```
## The library provides the following functions.

### LCD_putchar(char c)
Send character c to the display.

### clr_lcd()
Clears the display.

### gotoxy(char x,char y)
Position the cursor in the x and y position of the display.

### especial_char(char addr, char L1,char L2,char L3,char L4,char L5,char L6,char L7,char L8)
Creates a custom character at address addr with the pixels of lines L1 to L8.

### putstr(char *str)
Sends a string to the display.

### putuint(unsigned int data)
Converts an unsigned integer to text and sends it to the display.

### putint(int data)
Converts an integer to text and sends it to the display.

### LCD_init()
Initializes the display.

## An example program that uses the TextLCD.h library on an ATmega8 microcontroller is shown below.

```
#include <avr/io.h>
#include "TextLCD.h"

int main(void)
{
	unsigned int y=0;

	LCD_init(); // initializes lcd 20x4 (TextLCD.h)

	while(1)
	{
        gotoxy(2,1);
		putstr("y = ");
		putuint(y);
		putstr("      ");
		y++;
	}
}
```
