# TUGAS-EMBEDDED-SYSTEM
Jobsheet 1
// the setup function runs once when you press reset or power the board
void setup() {
  // initialize digital pin LED_BUILTIN as an output.
  pinMode(LED_BUILTIN, OUTPUT);
}

// the loop function runs over and over again forever
void loop() {
  digitalWrite(LED_BUILTIN, HIGH);  // turn the LED on (HIGH is the voltage level)
  delay(3000);                      // wait for a second
  digitalWrite(LED_BUILTIN, LOW);   // turn the LED off by making the voltage LOW
  delay(3000);                      // wait for a second
}


https://user-images.githubusercontent.com/118653054/202911256-d3fc6f78-d11e-46ee-887f-f34a1581a4ab.mp4

