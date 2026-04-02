# IoTAbsensi_Kelompok2

IoT Absensi adalah sistem pencatatan kehadiran yang bekerja secara otomatis dan terhubung ke jaringan (internet). 
Jika absensi tradisional menggunakan kertas atau tanda tangan, IoT Absensi menggunakan data biometrik (sidik jari) dan data waktu digital yang dikirim langsung ke database.

Komponen Absen IoT
ESP32
Fingerprint Sensor
LCD I2C 16x2
Buzzer
DS3231 (RTC)
Kabel dan Breadboard / PCB

Cara Kerja Sistem (Workflow)
Sistem ini bekerja dalam alur yang terintegrasi:
Identifikasi: Sensor R307 memindai sidik jari dan mengubahnya menjadi kode digital (ID).
Validasi Waktu: Modul RTC DS1307 memberikan data waktu (jam, menit, detik) yang akurat dan real-time tanpa perlu koneksi internet (karena ada baterai cadangan).
Pemrosesan: ESP32 mencocokkan ID jari dengan database. Jika cocok, ESP32 mengambil data waktu dari RTC.
Feedback: LCD menampilkan nama/ID dan waktu absen, sementara Buzzer berbunyi sebagai tanda proses berhasil.
Konektivitas (IoT): Karena menggunakan ESP32, data absen ini nantinya bisa dikirim ke Google Sheets, Database (MySQL), atau aplikasi Telegram melalui Wi-Fi.

