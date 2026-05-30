## FAN-SPEED-CONTROLLER-SYSTEM-USING-TEMPERATURE-SENSOR

## Aim:
To measure the Temperature using DHT11/DHT22/TMP36  sensor with Arduino UNO Board/ESP-32 using Tinker CAD.

## Hardware / Software Tools required:
PC/ Laptop with Internet connection
            Tinker CAD tool (Online)
	Arduino UNO Board/ESP-32
	Temperature Sensor (DHT11/DHT22/TMP36)

## Circuit Diagram:
   <img width="673" height="598" alt="image" src="https://github.com/user-attachments/assets/4b45998f-083f-4ed3-88cf-d72d783d5ff2" />

## Theory :
 The Arduino Uno is powered by the ATmega328P, an 8-bit microcontroller that runs at 16 MHz. It has 32 KB of flash memory, 2 KB of SRAM, and 1 KB of EEPROM. The board has 14 digital I/O pins (of which 6 can be used as PWM outputs) and 6 analog input pins. These pins allow the board to interface with various sensors, actuators, and other devices.The Arduino Uno can be powered via a USB connection or an external power supply. The board has a built-in voltage regulator to manage power from 7 to 12 volts.
The board is programmable using the Arduino IDE (Integrated Development Environment), which supports a simplified version of C/C++. The code, known as a "sketch," is uploaded to the board via a USB connection. The Uno has a USB-B port, which is used for communication with a computer. The USB connection also powers the board when connected. The board includes a reset button that restarts the microcontroller, useful during programming and troubleshooting. The In-Circuit Serial Programming (ICSP) header allows for low-level programming of the microcontroller or firmware updates. The Uno has a built-in LED on pin 13, commonly used for simple tests and debugging.
## Procedure:
Step 1: Set Up the Tinkercad Environment
	1.Log in to Tinkercad: Open Tinkercad in your web browser and log in to your account.
	2.Create a New Circuit: In the Tinkercad dashboard, click on "Circuits" and then select "Create New Circuit."
Step 2: Add Components to the Circuit
	1.Arduino Uno: Drag an Arduino Uno board from the components panel onto the workspace.
	2.TMP36 Sensor: Search for the TMP36 sensor in the components panel and drag it into the workspace.
	3.Breadboard: Drag a small breadboard to the workspace to help with wiring connections.
	4.Resistor (Optional): A resistor may not be necessary for this simple setup, but you can include it for more accurate readings.
	5.Wires: Use wires to connect the components.


Step 3: Connect the TMP36 Sensor to the Arduino
	1.TMP36 Pins:
	oVout (Middle Pin): Connect this to an analog input pin on the Arduino (e.g., A0).
	oGND (Right Pin): Connect this pin to the ground (GND) on the Arduino.
	oVs (Left Pin): Connect this to the 5V pin on the Arduino.
	2.Breadboard Wiring:
	oTMP36 Vout (Middle Pin) to Arduino A0: Use a wire to connect the middle pin (Vout) of the TMP36 sensor to the A0 analog input pin on the Arduino.
	oTMP36 GND (Right Pin) to Breadboard GND Rail: Connect the GND pin of the TMP36 sensor to the ground rail of the breadboard.
	oTMP36 Vs (Left Pin) to Breadboard 5V Rail: Connect the Vs pin of the TMP36 sensor to the 5V rail of the breadboard.
	oArduino GND to Breadboard GND Rail: Connect a wire from the Arduino GND pin to the ground rail on the breadboard.
	oArduino 5V to Breadboard 5V Rail: Connect a wire from the Arduino 5V pin to the power rail on the breadboard.
Step 4: Write the Arduino Code
	1.Code Editor: Click on the "Code" button at the top of the Tinkercad workspace to open the code editor.
	2.Set the Coding Mode: Ensure the editor is in "Text" mode to write your code in C/C++.
	3.Enter the Code: Write the following code to read the temperature from the TMP36 sensor
Step 5: Simulate the Circuit
	1.Start Simulation: Click the "Start Simulation" button at the top of the workspace to run the circuit and code.
	2.Monitor Output: Open the serial monitor by clicking the "Serial Monitor" button to view the temperature readings in both Celsius and Fahrenheit.
Step 6: Troubleshoot and Refine
	1.Check Connections: Ensure that all connections are made correctly on the breadboard and the Arduino.
	2.Adjust Code: If needed, tweak the code to improve accuracy or change the format of the output.
Step 7: Save Your Work
	1.Stop Simulation: Click "Stop Simulation" to end the simulation.
	2.Save the Circuit: Click "Save" to keep your circuit design and code for future use.

## Program: TMP36 Temperature and Humidity sensor interfacing with Ardiuno Board
```
const int analogIn = A0;
int humiditysensorOutput = 0;
// Defining Variables
int RawValue= 0;
double Voltage = 0;
double tempC = 0;
double tempF = 0;
void setup(){  
  Serial.begin(9600);
  pinMode(A1, INPUT);
}
void loop(){
  RawValue = analogRead(analogIn);
  Voltage = (RawValue / 1023.0) * 5000; // 5000 to get millivots.
  tempC = (Voltage-500) * 0.1; // 500 is the offset
  tempF = (tempC * 1.8) + 32; // convert to F  
  Serial.print("Raw Value = " );                  
  Serial.print(RawValue);      
  Serial.print("\t milli volts = ");
  Serial.print(Voltage,0); //
  Serial.print("\t Temperature in C = ");
  Serial.print(tempC,1);
  Serial.print("\t Temperature in F = ");
  Serial.println(tempF,1);
  humiditysensorOutput = analogRead(A1);
  Serial.print("Humidity: "); // Printing out Humidity Percentage
  Serial.print(map(humiditysensorOutput, 0, 1023, 10, 70));
  Serial.println("%");
  delay(5000);  //iterate every 5 seconds
}
```
## Output:
<img width="527" height="247" alt="image" src="https://github.com/user-attachments/assets/142d09d1-f101-4a1e-8460-f197ad2cef60" />


## RESULT:
The temperature and humidity values are measured using DHT11/DHT22/TMP36 sensor with Arduino UNO Board/ESP-32 and Simulated using Tinker CAD.
