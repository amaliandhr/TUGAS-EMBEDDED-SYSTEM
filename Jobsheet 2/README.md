## ESP32 Capacitive Touch Sensor
![image](https://user-images.githubusercontent.com/118653054/210950445-123696ed-95f6-4ee5-a782-be4e45adf856.png)
Pada script program tersebut membaca nilai sentuh dari pin yang sudah ditentukan dan akan menghidupkan LED ketika nilai yang dibaca berada dibawah nilai batas ambang. Dapat diartikan bahwa LED akan menyala ketika kabel jumper disentuh dan akan mati ketika tidak disentuh.
## Mengakses Sensor DHT 11 (Single Wire / BUS)
![image](https://user-images.githubusercontent.com/118653054/210951494-4e22f939-dd65-47a8-ab27-1c13e083ee1f.png)
Pada script program tersebut akan membaca suhu dan kelembapan udara yang ada di sekitar DHT dan nilai suhu tersebut akan muncul di serial monitor pada arduino.
Ini merupakan inisiasi library sensor DHT 11.
![image](https://user-images.githubusercontent.com/118653054/210952278-edb8d8c8-2ee5-4e29-9164-4f540b1baa2b.png)
Script program ini menjelaskan pin yang akan digunakan untuk pembacaan sensor yaitu pinD4 dan sensor DHT yang akan digunakan adalah tipe DHT11.
![image](https://user-images.githubusercontent.com/118653054/210952732-d968a78c-f1f7-45f6-88ec-057a1c18ad73.png)
Serial.begin(9600) digunakan untuk memulai komunikasi serial dengan frekuensi 9600KHz. Script dht.begin() untuk memulai pembacaan sensor dht.11.
![image](https://user-images.githubusercontent.com/118653054/210953158-99e7d666-278d-416f-a28b-b3c9c19fb585.png)
Variabel h engan tipe data float untuk variabel yang membaca kelembapan sedangkan untuk suhudibaca oleh variabel t.
![image](https://user-images.githubusercontent.com/118653054/210953567-74a6b0d8-369d-405f-aeb6-2bf55cb9fd0d.png)
nilai suhu dan kelembapan yang telah dibaca akan ditampilkan pada serial monitor.
## Mengakses Sensor RFID (SPI Communication)
![image](https://user-images.githubusercontent.com/118653054/210954239-0d881462-ede5-4839-9ac3-534637240bb4.png)
Pada script program tersebut membaca keyTagUID dari kartu yang akan digunakan dan akan menghidupkan LED. Apabila kartu didekatkan pada reader dan tagUID kartu benar maka LED akan menyala. LED mati apabila tagUID tidak dikenali.
