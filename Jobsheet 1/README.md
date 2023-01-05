
# DASAR PEMROGRAMAN ESP32 UNTUK PEMROSESAN DATA INPUT/OUTPUT ANALOG DAN DIGITAL
## GPIO
Pada dua baris kode ini akan membuat variable untuk menetapkan pin.
Const int buttonPin
Push button terhubung pada GPIO 18 dan LED terhubung pada GPIO 5. Selanjutnya, kode ini menentapkan default dari push button yaitu 0 ( tidah ditekan).
Int button state
Pada setup() berfungsi untuk mengkontrol bit per transfer data per detik. Kemudian, diinisialisasikan push button sebagai input dan LED sebagai output.
Void setup(){
Serial.begin
Paada loop() berfungsi apabila (buttonState==HIGH) berarti push button saat ditekan, LeD akan menyala dengan fungsi digital Write() yang dapat diset HIGH. Namun, apabila (buttonState==LOW) maka pushbutton todak ditekan dan LED tidak menyala karena digitalWrite() diset LOW.
Void loop() {
//
## Hasil Praktimum

## Kesimpulan
Pada praktikum ini dapat disimpulkan bahwa push button dapat digunakan untuk mengendalikan LED. Pin-pin yang akan digunakan dapat disesuaikan dengan input output serta keluaran yang diinginkan pada LEDnya. 
PWM
Pada praktikum ini kita mendapatkan sinyal yang sama dari saluran yang sama dalam GPIO yang berbeda. Agar dapat memenuhi itu hanya perlu menambahkan GPIO ke saluran yang sama pada setup() dengan program seperti berikut.
//the number
kode ini menetakan dua variable untuk dua LED, pada GPIO17 dan GPIO5. 
Const int led
Pada setup() ditambahkan baris untuk menetapkan dua GPIO ke saluran 0. Dapat diartikan bahwa sinyal yang sama dihasilkan pada saluran 0 dikedua GPIO.
ledAttachPin(
