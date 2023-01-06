
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
### A. GPIO
#### LED 1

https://user-images.githubusercontent.com/118653054/210912883-6a37a2f0-07b3-4bc3-a916-988478a02f86.mp4

#### LED 2 


https://user-images.githubusercontent.com/118653054/210914742-a12daf49-2f54-4e56-8f0e-b51b4143683e.mp4

#### LED 5



https://user-images.githubusercontent.com/118653054/210914758-61538e8b-df3b-4909-b09c-f6379c0d3d9f.mp4


#### BLINK


https://user-images.githubusercontent.com/118653054/210913553-200d44df-4c00-4bec-ab16-7a4e4d288b79.mp4



https://user-images.githubusercontent.com/118653054/210913562-3a45d675-5d53-468c-bd84-9514246f9429.mp4



https://user-images.githubusercontent.com/118653054/210913574-618e5f47-bab1-47f2-a179-4e34deeaeec9.mp4



https://user-images.githubusercontent.com/118653054/210913581-eb469b2f-7619-4359-8897-8928f4700593.mp4



### B. PWM
#### PWM 1


https://user-images.githubusercontent.com/118653054/210915800-1e548b55-407e-4162-9191-29e25e700b48.mp4

#### PWM 2


https://user-images.githubusercontent.com/118653054/210915816-62ea0eff-31ac-4a42-b081-6ed60031ee5b.mp4


### C. ADC dan DAC
#### ADC DAC 1


https://user-images.githubusercontent.com/118653054/210915910-a69ae683-7b15-4c5a-b17e-983b21fa6068.mp4

#### ADC DAC 2


https://user-images.githubusercontent.com/118653054/210915995-3bdc7875-09a7-4a85-bf83-0e98bddc0df8.mp4


## Kesimpulan
Pada praktikum ini dapat disimpulkan bahwa push button dapat digunakan untuk mengendalikan LED. Pin-pin yang akan digunakan dapat disesuaikan dengan input output serta keluaran yang diinginkan pada LEDnya. 
PWM
Pada praktikum ini kita mendapatkan sinyal yang sama dari saluran yang sama dalam GPIO yang berbeda. Agar dapat memenuhi itu hanya perlu menambahkan GPIO ke saluran yang sama pada setup() dengan program seperti berikut.
//the number
kode ini menetakan dua variable untuk dua LED, pada GPIO17 dan GPIO5. 
Const int led
Pada setup() ditambahkan baris untuk menetapkan dua GPIO ke saluran 0. Dapat diartikan bahwa sinyal yang sama dihasilkan pada saluran 0 dikedua GPIO.
ledAttachPin(
