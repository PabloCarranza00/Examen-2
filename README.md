# Examen-2
Practica 2 ex 2
#include <LiquidCrystal.h>

LiquidCrystal lcd (12,11,5,4,3,2);

float A = 0.0;
float B = 0.0;
float C = 0.0;
float D = 0.0;
float E = 0.0;

void setup() 
{  
	lcd.begin(16,2);
	pinMode (A0,INPUT);
	Serial.begin(9600);

}

void loop() 
{
	D = analogRead(A0);
	A = (D*5)/1023;
	B = 10000*((5/A)-1);

	lcd.setCursor(2,0);
	lcd.print(" F: ");
	C = pow((B/6086.6),-1.41203);
	lcd.print(C);
	lcd.print(" N");
	lcd.setCursor(2,2);
	lcd.print(" W: ");
	E = C * 101.97;
	lcd.print(E);
	lcd.print(" g");
	delay(2000);
	lcd.clear();

}
