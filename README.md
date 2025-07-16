# 🖼️ Tampilan Gambar di ST7789 TFT LCD 240×240 (ESP32 / ESP8266)

Proyek ini menunjukkan bagaimana cara menampilkan **gambar berwarna full 240x240** ke layar **TFT ST7789** menggunakan Arduino dan library `TFT_eSPI`.

---

## 📦 Kebutuhan

- ESP32 / ESP8266
- ST7789 240×240 SPI TFT LCD
- Arduino IDE / PlatformIO
- Library:
  - [TFT_eSPI](https://github.com/Bodmer/TFT_eSPI)
  - SPI (biasanya sudah include)

---

## 🧰 Wiring ESP32 ke ST7789

| ST7789 Pin | ESP32 GPIO (Contoh) |
|------------|---------------------|
| VCC        | 3.3V                |
| GND        | GND                 |
| SCL (CLK)  | GPIO 25             |
| SDA (MOSI) | GPIO 26             |
| RES        | GPIO 4              |
| DC         | GPIO 2              |
| CS         | Tidak dipakai (ikatan ke GND) |

---

## ⚙️ Konfigurasi `TFT_eSPI`

1. Buka file "C:\Users\...\Documents\Arduino\libraries\TFT_eSPI\User_Setups\Setup24_ST7789.h"
2. Pastikan baris konfigurasi seperti ini:

#define TFT_MISO -1  // Tidak digunakan (ST7789 hanya pakai MOSI)
#define TFT_MOSI 26  // SDA
#define TFT_SCLK 25  // SCL
#define TFT_CS   -1  // Tidak digunakan
#define TFT_DC    2  // Data Command
#define TFT_RST   4  // Reset




## 🖼️ Konversi Gambar ke Format Array

Gunakan situs berikut untuk mengubah gambar menjadi array C:

🔗 [https://notisrac.github.io/FileToCArray/](https://notisrac.github.io/FileToCArray/)

**Langkah-langkah:**

1. Upload gambar PNG/JPG (ukuran **240×240**).
2. Pilih pengaturan:
   - **Format**: Decimal (000)
   - **Output type**: `uint16_t`
   - Centang: `static`, `const`, `PROGMEM`
   - Centang: `16bit RRRRRGGGGGGBBBBBB`
   - Resize: `240 x 240`
3. Klik **Convert**.
4. Copy hasilnya ke file bernama `gambar.h`

Contoh hasil (`gambar.h`):


## 🧪 Hasil

Jika berhasil, gambar akan muncul full di layar TFT ST7789 kamu 
---

## 📘 Referensi

- [TFT_eSPI Library](https://github.com/Bodmer/TFT_eSPI)
- [FileToCArray Converter](https://notisrac.github.io/FileToCArray/)
- [ST7789 Datasheet](https://www.displayfuture.com/Display/datasheet/controller/ST7789.pdf)

---

## 🪪 Lisensi

Proyek ini berlisensi **MIT License** – bebas digunakan dan dimodifikasi.

---

🎉 Selamat mencoba! Jika terbantu, jangan lupa beri ⭐ di repositori!
