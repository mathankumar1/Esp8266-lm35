# Esp8266-lm35
#Download Arduino IDE

#then follow this link to Arduino setup:- https://youtu.be/MzoETAzjITw

#open Arduino go to tools-->Board-->Board Manager-->type Esp8266 and install

# Again go to tools-->Board-->NodeMCU 1.0(ESP-12E Module)

#go to sketch-->include library-->Manage library-->type lm35 and install

#After finish set up use script from here


sript

int outputpin = A0;  //initializes/defines the output pin of the LM35 temperature sensor
                    //this sets the ground pin to LOW and the input voltage pin to high
void setup()
{
Serial.begin(9600);
}

void loop() //main loop
{
int analogValue = analogRead(outputpin);
float millivolts = (analogValue/1024.0) * 3300; //3300 is the voltage provided by NodeMCU
float celsius = millivolts/10;
Serial.print("in DegreeC=   ");
Serial.println(celsius);

//---------- Here is the calculation for Fahrenheit ----------//
float fahrenheit = ((celsius * 9)/5 + 32);
Serial.print(" in Farenheit=   ");
Serial.println(fahrenheit);
delay(1000);
}
