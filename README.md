# IoTAbsensi_Kelompok2

IoT Absensi adalah sistem pencatatan kehadiran yang bekerja secara otomatis dan terhubung ke jaringan (internet). 
Jika absensi tradisional menggunakan kertas atau tanda tangan, IoT Absensi menggunakan data biometrik (sidik jari) dan data waktu digital yang dikirim langsung ke database.

Komponen Absen IoT
1. ESP32
2. Fingerprint Sensor (R307)
3. LCD I2C 16x2
4. Buzzer (Lilypad Buzzer)
5. DS3231 (RTC)
6. Kabel dan Breadboard / PCB

Cara Kerja Sistem (Workflow)

Sistem ini bekerja dalam alur yang terintegrasi:
1. Identifikasi: Sensor R307 memindai sidik jari dan mengubahnya menjadi kode digital (ID).
2. Validasi Waktu: Modul RTC DS1307 memberikan data waktu (jam, menit, detik) yang akurat dan real-time tanpa perlu koneksi internet (karena ada baterai cadangan).
3. Pemrosesan: ESP32 mencocokkan ID jari dengan database. Jika cocok, ESP32 mengambil data waktu dari RTC.
4. Feedback: LCD menampilkan nama/ID dan waktu absen, sementara Buzzer berbunyi sebagai tanda proses berhasil.
5. Konektivitas (IoT): Karena menggunakan ESP32, data absen ini nantinya bisa dikirim ke Google Sheets, Database (MySQL), atau aplikasi Telegram melalui Wi-Fi.

| Warna  | Fungsi                |
| ------ | --------------------- |
| Merah  | VCC (3.3V / 5V)       |
| Biru   | GND                   |
| Kuning | Jalur SDA I2C         |
| Kuning | Jalur SCL I2C         |
| Hijau  | TX Fingerprint Sensor |
| Putih  | RX Fingerprint Sensor |
| Hitam  | Buzzer (digital pin)  |


<img width="2391" height="1188" alt="Absen Real-Time_Kelompok 2_bb" src="https://github.com/user-attachments/assets/3eec3db1-a5e9-48ca-891e-8868358913d1" />/>



