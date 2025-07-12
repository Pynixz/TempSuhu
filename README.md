# 🌡️ Simulasi IoT [Wokwi + ThingSpeak] - Monitoring Suhu dan Kelembaban dengan ESP32 & DHT22
Proyek ini adalah simulasi sistem monitoring suhu dan kelembaban berbasis IoT menggunakan **ESP32**, **sensor DHT22**, dan **platform ThingSpeak**. Simulasi dilakukan di lingkungan **Wokwi** untuk memudahkan pengujian tanpa perangkat keras fisik.

## 📌 Fitur Utama
- Monitoring suhu dan kelembaban secara real-time menggunakan sensor DHT22
- Pengiriman data ke platform ThingSpeak untuk visualisasi grafik
- Menampilkan data suhu & kelembaban di serial monitor dan layar OLED (simulasi)
- Dapat terkoneksi ke WiFi (Wokwi) secara otomatis

## 🧰 Alat & Bahan
- ESP32 (simulasi di Wokwi)
- Sensor DHT22
- OLED Display (opsional, untuk tampilan langsung)
- Platform IoT: [ThingSpeak](https://thingspeak.com)
- Simulasi: [Wokwi IoT Simulator](https://wokwi.com)
- Youtube : https://youtu.be/qbxj6CwLRD8?si=wBiLLCMMBKWNfLmu

## 🖼️ Dokumentasi Simulasi

### 🔌 Rangkaian & Kode
- DHT22 terhubung ke pin GPIO4 pada ESP32
- Komunikasi serial ke monitor menggunakan baud rate 9600
- Kode dikembangkan menggunakan Arduino IDE (atau simulasi di Wokwi)

## [Simulasi awal DHT22 & ESP32]
<img width="1919" height="862" alt="Screenshot 2025-07-12 193209" src="https://github.com/user-attachments/assets/b1b7e2e4-d513-4ca1-bcd6-498b1f73ff31" />
*Gambar 1: Pembacaan suhu dan kelembaban dari sensor*

##[WiFi connection dan OLED]
<img width="1919" height="864" alt="Screenshot 2025-07-12 193219" src="https://github.com/user-attachments/assets/03a48cf8-9606-4f5e-8969-cf2eaaa86a8a" />
*Gambar 2: ESP32 terkoneksi ke WiFi dan menampilkan data di OLED*

## 📈 Integrasi ThingSpeak
Data dikirim ke ThingSpeak secara berkala menggunakan koneksi WiFi. Grafik suhu, kelembaban, dan heat index dapat dipantau secara real-time.

Contoh hasil grafik:
- Humidity (Field 1)
- Temperature (Field 2)
- Heat Index (Field 3)

## [Grafik di ThingSpeak]
<img width="1919" height="862" alt="Screenshot 2025-07-12 193244" src="https://github.com/user-attachments/assets/fde0e118-556f-47d6-ba90-8778519eeb63" />

## 🧪 Contoh Kode Arduino (cuplikan)
```cpp
#include "DHT.h"
#define DHTPIN 4
#define DHTTYPE DHT22
DHT dht(DHTPIN, DHTTYPE);

void setup() {
  Serial.begin(9600);
  dht.begin();
}

void loop() {
  float hum = dht.readHumidity();
  float temp = dht.readTemperature();
  Serial.print("Kelembaban: ");
  Serial.print(hum);
  Serial.print("%  Suhu: ");
  Serial.print(temp);
  Serial.println("°C");
  delay(2000);
}


💡 Tujuan
Mempelajari dasar komunikasi sensor dan pengolahan data suhu/kelembaban

Menggunakan IoT untuk monitoring lingkungan secara daring

Praktik pengiriman data ke cloud dan menampilkannya secara visual

📝 Lisensi
Proyek ini bersifat open-source dan dapat digunakan untuk keperluan edukasi dan pengembangan pribadi.
