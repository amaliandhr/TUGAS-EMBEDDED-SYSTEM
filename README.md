# TUGAS-EMBEDDED-SYSTEM
Jobsheet 1
ADC_DAC
// Potentiometer is connected to GPIO 34 (Analog ADC1_CH6)
const int potPin = 34;
// variable for storing the potentiometer value
int potValue = 0;
void setup() {
Serial.begin(115200);
delay(1000);
}
void loop() {
// Reading potentiometer value
potValue = analogRead(potPin);
Serial.println(potValue);
delay(500);
}


https://user-images.githubusercontent.com/118653054/202909551-ed13adf0-13c0-4c2e-aea8-24a2a98843a2.mp4

