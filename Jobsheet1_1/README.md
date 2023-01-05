#  JARINGAN SENSOR NIRKABEL MENGGUNAKAN ESP-NOW
## 2-B-Sender
Pada baris kode library esp_now.h dan WiFi.h. untuk menghubungkan perangkat keras ESP32 dengan jaringan wifi.
include <esp_now.h>
include <WiFi.h>

Baris selanjutnya, harus memasukan alamat MAC penerima ESP32
// Ganti dengan Mac Address ESP32 Receiver
uint8_t broadcastAddress[] = {0x94, 0xB5, 0x55, 0x2C, 0x47, 0xB4};

Pada praktikum ini, alamat MAC pengirim adalah : 94 : B5 : 55 : 2C : 47 : B4. Buat struktur yang berisis tipe data yang ingin kita kirim dapat disebut dengan struct_message. Dalam struct_message ini berisi 4 jenis variable yang berbeda.
// Struktur pesan sender dan receiver harus sama
typedef struct struct_message {
 char a[32];
 int b;
 float c;
 bool d;
} struct_message;

Kemudian untuk membuat variable baru dengan tipe struct_message yang dapat disebut engan myData yang akan menyimpan nilai variable. Untuk variable tipe esp_now_peer_info_t berfungsi untuk menyimpan informasi tentang rekan.
// Driver untuk struktur pesan
struct_message myData;
esp_now_peer_info_t peerInfo;

fungsi callback ini adalah panggilan balik yang akan dijalankan ketika pesan dikirim. Dalam hal ini, fungsi hanya mencetak saat pesan dikirim atau tidak. Di setup(), inisialisasi monitor serial untuk keprluan debugging.
// fungsi callback
void OnDataSent(const uint8_t *mac_addr, esp_now_send_status_t status) {
 Serial.print("\r\nStatus Paket Terakhir :\t");
 Serial.println(status == ESP_NOW_SEND_SUCCESS ? "Sukses Terkirim" : "Gagal Terkirim");
}
void setup() {
 // Init Serial Monitor
 Serial.begin(115200)

Mengatur perangkat untuk stasiun Wi-Fi dan instalasi ESP-NOW.
// Set ESP32 sebagai station
 WiFi.mode(WIFI_STA);
// Init ESP-NOW
 if (esp_now_init() != ESP_OK) {
 Serial.println("Gagal menginisialisasi ESP-NOW");
 return;
 }

Buat fungsi callback yang akan dipanggil saat pesan dikirim.
// Fungsi akses register cb untuk perintah mengirim data
 esp_now_register_send_cb(OnDataSent);

Setelah itu pemasangan dengan perangkat ESP-NOW lain untuk mengirim data. 
// Register peer
 memcpy(peerInfo.peer_addr, broadcastAddress, 6);
 peerInfo.channel = 0;
 peerInfo.encrypt = false;

 // Add peer
 if (esp_now_add_peer(&peerInfo) != ESP_OK){
 Serial.println("Gagal menambahkan peer");
 return;
 }
}

Di loop(), ini akan mengirimkan pesan melalui ESP-NOW setiap 2 detik dengan menetapkan nilai variable. Dapat di ingat bahwa myData adalah sebuah struktur. Pada praktikum ini ditetapkan nilai yang di kirim ke dalam struktur seperti baris pertama karakter, baris kedua nomer Int acak, float, dan variable boolean
void loop() {
 // Set values to send
 strcpy(myData.a, "INI ADALAH CHAR");
 myData.b = random(1,250);
 myData.c = 1.2;
 myData.d = false;
// Send message via ESP-NOW
 esp_err_t result = esp_now_send(broadcastAddress, (uint8_t *) &myData,
sizeof(myData));

 if (result == ESP_OK) {
 Serial.println("Data berhasil terkirim");
 }
 else {
 Serial.println("Gagal mengirim data");
 }
 delay(2000);
 }
