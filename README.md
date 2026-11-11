<img width="1280" height="1280" alt="Hardware   Pinouts" src="https://github.com/user-attachments/assets/4aa5d6df-13ce-4cdf-9de9-755ee42142b9" />

🎵 ESP32 SD & Bluetooth Audio Player

[TH](ภาษาไทย) | [EN](English)

------------------------------

📌 เกี่ยวกับโปรเจกต์
โปรเจกต์ เครื่องเล่นเพลงมัลติมีเดียแบบพกพาโดยใช้ ESP32 ที่รองรับการเล่นไฟล์ MP3 จาก SD Card และรับสัญญาณเสียงแบบไร้สายผ่าน Bluetooth A2DP โดยแสดงผลผ่านจอ OLED SSD1306 ที่รองรับการแสดงผลภาษาไทยสมบูรณ์แบบ ควบคุมการทำงานทั้งหมดด้วย Rotary Encoder เพียงตัวเดียว

-----------------------------------------------------------------------------------------------------

✨ คุณสมบัติและฟังก์ชันการทำงาน
- 2 โหมดการทำงาน:
  - SD Card Mode: เล่นไฟล์ MP3 จาก SD Card (คัดแยกและเรียงลำดับชื่อไฟล์ให้อัตโนมัติ)
  - Bluetooth Audio Sink: รับสัญญาณเสียงสตรีมมิ่งจากสมาร์ทโฟน พร้อมแสดงชื่อเพลง/ศิลปิน
- ระบบหน้าจอและภาษา:
  - รองรับภาษาไทยและภาษาอังกฤษสมบูรณ์แบบ (เมนูภาษาไทย/อังกฤษ)
  - เอฟเฟกต์การสลับหน้าจอและระบบตัวหนังสือวิ่ง เมื่อชื่อเพลงยาวเกินหน้าจอ
  - แสดงระดับแบตเตอรี่ คำนวณเปอร์เซ็นต์จริงด้วยกราฟแรงดันไฟ
- ระบบการควบคุม :
  - ควบคุมง่ายด้วย (หมุนปรับระดับเสียง / เลือกเพลง)
  - ปุ่มกดรองรับ Multi-click (กด 1 ครั้งเล่น/หยุด, กด 2 ครั้งเปลี่ยนเพลงถัดไป, กด 3 ครั้งย้อนกลับ) และกดค้างเข้าสู่หน้าเมนู

------------------------------------------------------------------------------------------------------

🛠️ อุปกรณ์ฮาร์ดแวร์และต่อขาพิน (Hardware & Pinouts)

| อุปกรณ์ | ขาพิน ESP32 (Pin) |
------------------------------
| **I2S DAC / Amplifier** | BCK: `GPIO 26`, LRCK: `GPIO 25`, DATA: `GPIO 27` |
| **SD Card Module (SPI)** | CLK: `GPIO 18`, MISO: `GPIO 19`, MOSI: `GPIO 23`, CS: `GPIO 13` |
| **OLED Display (I2C 128x64)** | SDA: `GPIO 21`, SCL: `GPIO 22` |
| **Rotary Encoder** | CLK: `GPIO 32`, DT: `GPIO 33`, SW: `GPIO 14` |
| **Battery Voltage Sensing** | ADC Pin: `GPIO 34` |

------------------------------------------------------------------------------------------------------

### 📥 ขั้นตอนการแฟลชไฟล์ `.bin` (Installation & Flashing)

ผู้ใช้งานไม่จำเป็นต้องลงโปรแกรมหรือตั้งค่าไลบรารีใน Arduino IDE สามารถติดตั้งไฟล์โปรแกรม `.bin` ผ่านเว็บเบราว์เซอร์ได้ทันที:

1. เตรียมอุปกรณ์:**
   - สาย USB-C / Micro-USB ที่รองรับการส่งข้อมูล (Data Cable)
   - เชื่อมต่อบอร์ด ESP32 เข้ากับคอมพิวเตอร์
2. เปิดเว็บไซต์ ESPTool:**
   - เข้าไปที่ [ESPTool Web Application](https://espressif.github.io/esptool-js/)
3. เชื่อมต่อบอร์ด:**
   - กดปุ่ม **Connect** บนหน้าเว็บ แล้วเลือกพอร์ต Serial/COM Port ของ ESP32
4. ตั้งค่าการแฟลชไฟล์:**
   - กำหนด Flash Address และเลือกไฟล์ `.bin`:
     - **Address `0x0000`** -> เลือกไฟล์ `firmware.bin`
5. **เริ่มการติดตั้ง:**
   - กดปุ่ม **Program** แล้วรอจนกระบวนการแฟลชเสร็จสมบูรณ์ 100%
   - กดปุ่ม **Reset (EN)** บนบอร์ด ESP32 เพื่อเริ่มใช้งาน


------------------------------------------------------------------------------------------------------------


🎵 ESP32 SD & Bluetooth Audio Player

📌 About the Project
A portable multimedia audio player project using the ESP32, supporting MP3 playback from an SD Card and wireless audio streaming via Bluetooth A2DP. It features an OLED SSD1306 display with full Thai language rendering support and is fully controlled using a single Rotary Encoder.

-----------------------------------------------------------------------------------------------------

✨ Features & Functionalities
- 2 Operating Modes:
  - SD Card Mode: Plays MP3 files from an SD Card (automatically sorts file names).
  - Bluetooth Audio Sink: Streams wireless audio from a smartphone with real-time song title and artist display.
- Display & Language System:
  - Full Thai and English language support (Thai/English UI menus).
  - Smooth screen transition effects and auto-scrolling marquee text for long song titles.
  - Real-time battery indicator with accurate percentage calculation based on discharge voltage curves.
- Control System:
  - Intuitive navigation (Rotate to adjust volume / navigate track list).
  - Multi-click push button support (Single-click: Play/Pause, Double-click: Next track, Triple-click: Previous track, Long-press: Open Menu).

------------------------------------------------------------------------------------------------------

🛠️ Hardware & Pinouts

| Component | ESP32 Pin Assignment |
| :--- | :--- |
| **I2S DAC / Amplifier** | BCK: `GPIO 26`, LRCK: `GPIO 25`, DATA: `GPIO 27` |
| **SD Card Module (SPI)** | CLK: `GPIO 18`, MISO: `GPIO 19`, MOSI: `GPIO 23`, CS: `GPIO 13` |
| **OLED Display (I2C 128x64)** | SDA: `GPIO 21`, SCL: `GPIO 22` |
| **Rotary Encoder** | CLK: `GPIO 32`, DT: `GPIO 33`, SW: `GPIO 14` |
| **Battery Voltage Sensing** | ADC Pin: `GPIO 34` |

------------------------------------------------------------------------------------------------------

📥 Installation & Flashing (.bin Firmware)

No need to install the Arduino IDE or configure libraries. You can flash the compiled `.bin` firmware directly through your web browser:

1. **Prepare Requirements:**
   - A USB-C / Micro-USB cable that supports data transfer.
   - Connect the ESP32 board to your computer.
2. **Open ESPTool Web Application:**
   - Go to the [ESPTool Web Application](https://espressif.github.io/esptool-js/).
3. **Connect the Board:**
   - Click the **Connect** button on the website and select the Serial/COM Port corresponding to your ESP32.
4. **Configure Flash Settings:**
   - Set the Flash Address and select your `.bin` file:
     - **Address `0x0000`** -> Select `firmware.bin`
5. **Start Installation:**
   - Click the **Program** button and wait until the flashing process reaches 100%.
   - Press the **Reset (EN)** button on the ESP32 board to start using the device.
