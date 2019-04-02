# Text LCD display library for AVR Microcontrollers
A small library for use of text LCD in 4 bit mode on AVR microcontrollers

##How to use the library:
To configure the library, select the appropriate pins and ports on the first lines of code in the textLCD.h file, depending on the display connections in your circuit.

##Here's an example:
To connect the display to the following pins,
LCD data 4 - AVR PB2
LCD data 5 - AVR PB3
LCD data 6 - AVR PB4
LCD data 7 - AVR PB5
LCD E - AVR PB1
LCD RS - AVR PB0
LCD RW - GND

The textLCD.h file should look like this.

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
