## ทดสอบ Build และ Run (ครั้งที่ 1)
```
root@e0a2c7e8dd44:/project/lab6_2_multiple_files# idf.py qemu
Adding "qemu"'s dependency "all" to list of commands with default set of options.
Executing action: all (aliases: build)
Running ninja in directory /project/lab6_2_multiple_files/build
Executing "ninja all"...
[1/4] cd /project/lab6_2_multiple_files/build/esp-idf/esptool_py && /opt/esp/python_env/idf6.0...ition_table/partition-table.bin /project/lab6_2_multiple_files/build/lab6_2_multiple_files.bi 
lab6_2_multiple_files.bin binary size 0x27d50 bytes. Smallest app partition is 0x100000 bytes. 0xd82b0 bytes (84%) free.
[1/1] cd /project/lab6_2_multiple_files/build/bootloader/esp-idf/esptool_py && /opt/esp/python...offset 0x8000 bootloader 0x1000 /project/lab6_2_multiple_files/build/bootloader/bootloader.bi 
Bootloader binary size 0x66a0 bytes. 0x960 bytes (8%) free.
[4/4] Completed 'bootloader'Executing action: qemu
Generating flash image: /project/lab6_2_multiple_files/build/qemu_flash.bin
esptool.py --chip=esp32 merge_bin --output=/project/lab6_2_multiple_files/build/qemu_flash.bin --fill-flash-size=2MB --flash_mode dio --flash_freq 40m --flash_size 2MB 0x1000 bootloader/bootloader.bin 0x10000 lab6_2_multiple_files.bin 0x8000 partition_table/partition-table.bin
esptool.py v4.9.0
SHA digest in image updated
Wrote 0x200000 bytes to file /project/lab6_2_multiple_files/build/qemu_flash.bin, ready to flash to offset 0x0
Using existing efuse image: /project/lab6_2_multiple_files/build/qemu_efuse.bin
Running qemu (fg): qemu-system-xtensa -M esp32 -m 4M -drive file=/project/lab6_2_multiple_files/build/qemu_flash.bin,if=mtd,format=raw -drive file=/project/lab6_2_multiple_files/build/qemu_efuse.bin,if=none,format=raw,id=efuse -global driver=nvram.esp32.efuse,property=drive,value=efuse -global driver=timer.esp32.timg,property=wdt_disable,value=true -nic user,model=open_eth -nographic -serial mon:stdio
Adding SPI flash device
ets Jul 29 2019 12:21:46

rst:0x1 (POWERON_RESET),boot:0x12 (SPI_FAST_FLASH_BOOT)
configsip: 0, SPIWP:0xee
clk_drv:0x00,q_drv:0x00,d_drv:0x00,cs0_drv:0x00,hd_drv:0x00,wp_drv:0x00
mode:DIO, clock div:2
load:0x3fff0030,len:6372
load:0x40078000,len:15928
load:0x40080400,len:3880
entry 0x40080638
I (1001) boot: ESP-IDF v6.0-dev-1002-gbfe5caf58f 2nd stage bootloader
I (1003) boot: compile time Aug  8 2025 15:25:31
I (1005) boot: Multicore bootloader
I (1384) boot: chip revision: v3.0
I (1388) boot.esp32: SPI Speed      : 40MHz
I (1389) boot.esp32: SPI Mode       : DIO
I (1389) boot.esp32: SPI Flash Size : 2MB
I (1445) boot: Enabling RNG early entropy source...
I (1509) boot: Partition Table:
I (1509) boot: ## Label            Usage          Type ST Offset   Length
I (1510) boot:  0 nvs              WiFi data        01 02 00009000 00006000
I (1511) boot:  1 phy_init         RF data          01 01 0000f000 00001000
I (1511) boot:  2 factory          factory app      00 00 00010000 00100000
I (1564) boot: End of partition table
I (1937) esp_image: segment 0: paddr=00010020 vaddr=3f400020 size=09634h ( 38452) map
I (2125) esp_image: segment 1: paddr=0001965c vaddr=3ff80000 size=00024h (    36) load
I (2309) esp_image: segment 2: paddr=00019688 vaddr=3ffb0000 size=025e0h (  9696) load
I (2513) esp_image: segment 3: paddr=0001bc70 vaddr=40080000 size=043a8h ( 17320) load
I (2712) esp_image: segment 4: paddr=00020020 vaddr=400d0020 size=0f0ach ( 61612) map
I (2903) esp_image: segment 5: paddr=0002f0d4 vaddr=400843a8 size=08c58h ( 35928) load
I (3406) boot: Loaded app from partition at offset 0x10000
I (3407) boot: Disabling RNG early entropy source...
I (3475) cpu_start: Multicore app
I (6493) cpu_start: Pro cpu start user code
I (6496) cpu_start: cpu freq: 160000000 Hz
I (6498) app_init: Application information:
I (6498) app_init: Project name:     lab6_2_multiple_files
I (6500) app_init: App version:      1
I (6500) app_init: Compile time:     Aug  8 2025 15:24:56
I (6500) app_init: ELF file SHA256:  ade90ac1d...
I (6501) app_init: ESP-IDF:          v6.0-dev-1002-gbfe5caf58f
I (6502) efuse_init: Min chip rev:     v0.0
I (6502) efuse_init: Max chip rev:     v3.99
I (6502) efuse_init: Chip rev:         v3.0
I (6504) heap_init: Initializing. RAM available for dynamic allocation:
I (6506) heap_init: At 3FFAE6E0 len 00001920 (6 KiB): DRAM
I (6507) heap_init: At 3FFB2EA8 len 0002D158 (180 KiB): DRAM
I (6508) heap_init: At 3FFE0440 len 00003AE0 (14 KiB): D/IRAM
I (6509) heap_init: At 3FFE4350 len 0001BCB0 (111 KiB): D/IRAM
I (6510) heap_init: At 4008D000 len 00013000 (76 KiB): IRAM
I (6584) spi_flash: detected chip: winbond
I (6591) spi_flash: flash io: dio
I (6610) main_task: Started on CPU0
I (6620) main_task: Calling app_main()
I (6620) MAIN: 🚀 Lab 6.2: Multiple Source Files Demo
I (6620) MAIN: 📍 Main function from file: ./main/lab6_2_multiple_files.c, line: 13
I (6620) MAIN: ESP-IDF Version: v6.0-dev-1002-gbfe5caf58f
I (6620) SENSOR: 🔧 Sensor initialized from file: ./main/sensor.c, line: 12
I (6630) SENSOR: 📡 Sensor module ready for operation
I (6630) MAIN: === Loop 0 ===
I (6630) SENSOR: 📊 Reading sensor data from file: ./main/sensor.c, line: 18
I (6630) SENSOR: 🌡️  Temperature: 30.4°C
I (6640) SENSOR: 💧 Humidity: 93.6%
I (8640) MAIN: === Loop 1 ===
I (8640) SENSOR: 📊 Reading sensor data from file: ./main/sensor.c, line: 18
I (8640) SENSOR: 🌡️  Tempera ture: 34.9°C
I (8640) SENSOR: 💧 Humidity: 96.5%
I (10640) MAIN: === Loop 2 ===
I (10640) SENSOR: 📊 Reading sensor data from file: ./main/sensor.c, line: 18
I (10640) SENSOR: 🌡️  T emperature: 27.0°C
I (10640) SENSOR: 💧 Humidity: 89.5%
I (10640) SENSOR: ✅ Sensor status check from file: ./main/sensor.c, line: 30
I (10640) SENSOR: 📈 All sensors operating normally
I (12640) MAIN: === Loop 3 ===
I (12640) SENSOR: 📊 Reading sensor data from file: ./main/sensor.c, line: 18
I (12640) SENSOR: 🌡️  Temperature: 26.0°C
I (12640) SENSOR: 💧 Humidity: 99.2%
I (14640) MAIN: === Loop 4 ===
I (14640) SENSOR: 📊 Reading sensor data from file: ./main/sensor.c, line: 18
I (14640) SENSOR: 🌡️  Temperature: 30.3°C
I (14640) SENSOR: 💧 Humidity: 62.3%
I (16640) MAIN: === Loop 5 ===
I (16640) SENSOR: 📊 Reading sensor data from file: ./main/sensor.c, line: 18
I (16640) SENSOR: 🌡️  Temperature: 33.7°C
I (16640) SENSOR: 💧 Humidity: 69.8%
I (16640) SENSOR: ✅ Sensor status check from file: ./main/sensor.c, line: 30
I (16640) SENSOR: 📈 All sensors operating normally
I (18640) MAIN: === Loop 6 ===
I (18640) SENSOR: 📊 Reading sensor data from file: ./main/sensor.c, line: 18
I (18640) SENSOR: 🌡️  Temperature: 25.8°C
I (18640) SENSOR: 💧 Humidity: 89.4%
```
## ทดสอบ Build และ Run ขั้นสุดท้าย
```
rst:0x1 (POWERON_RESET),boot:0x12 (SPI_FAST_FLASH_BOOT)
configsip: 0, SPIWP:0xee
clk_drv:0x00,q_drv:0x00,d_drv:0x00,cs0_drv:0x00,hd_drv:0x00,wp_drv:0x00
mode:DIO, clock div:2
load:0x3fff0030,len:6372
load:0x40078000,len:15928
load:0x40080400,len:3880
entry 0x40080638
I (1170) boot: ESP-IDF v6.0-dev-1002-gbfe5caf58f 2nd stage bootloader
I (1172) boot: compile time Aug  8 2025 16:14:29
I (1172) boot: Multicore bootloader
I (1608) boot: chip revision: v3.0
I (1612) boot.esp32: SPI Speed      : 40MHz
I (1612) boot.esp32: SPI Mode       : DIO
I (1613) boot.esp32: SPI Flash Size : 2MB
I (1679) boot: Enabling RNG early entropy source...
I (1761) boot: Partition Table:
I (1761) boot: ## Label            Usage          Type ST Offset   Length
I (1762) boot:  0 nvs              WiFi data        01 02 00009000 00006000
I (1764) boot:  1 phy_init         RF data          01 01 0000f000 00001000
I (1765) boot:  2 factory          factory app      00 00 00010000 00100000
I (1842) boot: End of partition table
I (2339) esp_image: segment 0: paddr=00010020 vaddr=3f400020 size=09a24h ( 39460) map
I (2689) esp_image: segment 1: paddr=00019a4c vaddr=3ff80000 size=00024h (    36) load
I (2969) esp_image: segment 2: paddr=00019a78 vaddr=3ffb0000 size=025e0h (  9696) load
I (3190) esp_image: segment 3: paddr=0001c060 vaddr=40080000 size=03fb8h ( 16312) load
I (3431) esp_image: segment 4: paddr=00020020 vaddr=400d0020 size=0f3e4h ( 62436) map
I (3649) esp_image: segment 5: paddr=0002f40c vaddr=40083fb8 size=09048h ( 36936) load
I (4246) boot: Loaded app from partition at offset 0x10000
I (4247) boot: Disabling RNG early entropy source...
I (4312) cpu_start: Multicore app
I (8083) cpu_start: Pro cpu start user code
I (8086) cpu_start: cpu freq: 160000000 Hz
I (8088) app_init: Application information:
I (8088) app_init: Project name:     lab6_2_multiple_files
I (8088) app_init: App version:      1
I (8089) app_init: Compile time:     Aug  8 2025 16:14:05
I (8090) app_init: ELF file SHA256:  2c1b8b0dd...
I (8090) app_init: ESP-IDF:          v6.0-dev-1002-gbfe5caf58f
I (8091) efuse_init: Min chip rev:     v0.0
I (8091) efuse_init: Max chip rev:     v3.99
I (8091) efuse_init: Chip rev:         v3.0
I (8093) heap_init: Initializing. RAM available for dynamic allocation:
I (8095) heap_init: At 3FFAE6E0 len 00001920 (6 KiB): DRAM
I (8095) heap_init: At 3FFB2EB0 len 0002D150 (180 KiB): DRAM
I (8096) heap_init: At 3FFE0440 len 00003AE0 (14 KiB): D/IRAM
I (8096) heap_init: At 3FFE4350 len 0001BCB0 (111 KiB): D/IRAM
I (8096) heap_init: At 4008D000 len 00013000 (76 KiB): IRAM
I (8158) spi_flash: detected chip: winbond
I (8166) spi_flash: flash io: dio
I (8191) main_task: Started on CPU0
I (8201) main_task: Calling app_main()
I (8201) MAIN: 🚀 Lab 6.2: Multiple Source Files Demo
I (8201) MAIN: 📍 Main function from file: ./main/lab6_2_multiple_files.c, line: 15
I (8211) MAIN: ESP-IDF Version: v6.0-dev-1002-gbfe5caf58f
I (8211) SENSOR: 🔧 Sensor initialized from file: ./main/sensor.c, line: 12
I (8211) SENSOR: 📡 Sensor module ready for operation
I (8211) DISPLAY: 🖥️   Display initialized from file: ./main/display.c, line: 9
I (8211) DISPLAY: 💡 Display module ready
I (8211) LED: 💡 LED initialized from file: ./main/led.c, line: 12
I (8211) LED: 🔧 LED module ready
I (8211) DISPLAY: 📢 Displaying from file: ./main/display.c, line: 15
I (8211) DISPLAY: 📺 Message: System Starting...
I (8211) LED: 🚀 Starting LED blink task from file: ./main/led.c, line: 59
I (8221) LED: ✨ LED blink task started from file: ./main/led.c, line: 49
I (8221) LED: ✅ LED ON from file: ./main/led.c, line: 20
I (8221) LED: 🟢 LED is now ON
I (8221) LED: 🔄 LED toggled from file: ./main/led.c, line: 38
I (8221) MAIN: === Loop 0 ===
I (8221) DISPLAY: 🧹 Screen cleared from file: ./main/display.c, line: 28
I (8221) DISPLAY: ✨ Display ready for new content
I (8221) SENSOR: 📊 Reading sensor data from file: ./main/sensor.c, line: 18
I (8221) SENSOR: 🌡️  Temperature:  28.8°C
I (8241) SENSOR: 💧 Humidity: 61.7%
I (8241) DISPLAY: 📊 Data display from file: ./main/display.c, line: 21
I (8241) DISPLAY: 📈 Value 1: 26.50
I (8241) DISPLAY: 📉 Value 2: 61.00
I (8241) DISPLAY: 📢 Displaying from file: ./main/display.c, line: 15
I (8241) DISPLAY: 📺 Message: LED Status: ON
I (10241) MAIN: === Loop 1 ===
I (10241) DISPLAY: 🧹 Screen cleared from file: ./main/display.c, line: 28
I (10241) DISPLAY: ✨ Display ready for new content
I (10241) SENSOR: 📊 Reading sensor data from file: ./main/sensor.c, line: 18
I (10241) SENSOR: 🌡️  Temperature: 31.1°C
I (10241) SENSOR: 💧 Humidity: 75.2%
I (10241) DISPLAY: 📊 Data display from file: ./main/display.c, line: 21
I (10241) DISPLAY: 📈 Value 1: 27.50
I (10251) DISPLAY: 📉 Value 2: 62.00
I (10251) DISPLAY: 📢 Displaying from file: ./main/display.c, line: 15
I (10251) DISPLAY: 📺 Message: LED Status: ON
I (11221) LED: ❌ LED OFF from file: ./main/led.c, line: 27
I (11221) LED: 🔴 LED is now OFF
I (11221) LED: 🔄 LED toggled from file: ./main/led.c, line: 38
I (12251) MAIN: === Loop 2 ===
I (12251) DISPLAY: 🧹 Screen cleared from file: ./main/display.c, line: 28
I (12251) DISPLAY: ✨ Display ready for new content
I (12251) SENSOR: 📊 Reading sensor data from file: ./main/sensor.c, line: 18
I (12251) SENSOR: 🌡️  Temperature: 30.4°C
I (12251) SENSOR: 💧 Humidity: 78.7%
I (12251) DISPLAY: 📊 Data display from file: ./main/display.c, line: 21
I (12261) DISPLAY: 📈 Value 1: 28.50
I (12261) DISPLAY: 📉 Value 2: 63.00
I (12261) DISPLAY: 📢 Displaying from file: ./main/display.c, line: 15
I (12261) DISPLAY: 📺 Message: LED Status: OFF
I (12261) SENSOR: ✅ Sensor status check from file: ./main/sensor.c, line: 30
I (12261) SENSOR: 📈 All sensors operating normally
I (12261) DISPLAY: 📢 Displaying from file: ./main/display.c, line: 15
I (12261) DISPLAY: 📺 Message: Status Check Complete
I (14221) LED: ✅ LED ON from file: ./main/led.c, line: 20
I (14221) LED: 🟢 LED is now ON
I (14221) LED: 🔄 LED toggled from file: ./main/led.c, line: 38
I (14261) MAIN: === Loop 3 ===
I (14261) DISPLAY: 🧹 Screen cleared from file: ./main/display.c, line: 28
I (14261) DISPLAY: ✨ Display ready for new content
I (14261) SENSOR: 📊 Reading sensor data from file: ./main/sensor.c, line: 18
I (14261) SENSOR: 🌡️  Temperature: 32.2°C
I (14261) SENSOR: 💧 Humidity: 74.3%
I (14261) DISPLAY: 📊 Data display from file: ./main/display.c, line: 21
I (14261) DISPLAY: 📈 Value 1: 29.50
I (14261) DISPLAY: 📉 Value 2: 64.00
I (14261) DISPLAY: 📢 Displaying from file: ./main/display.c, line: 15
I (14261) DISPLAY: 📺 Message: LED Status: ON
I (16261) MAIN: === Loop 4 ===
I (16261) DISPLAY: 🧹 Screen cleared from file: ./main/display.c, line: 28
I (16261) DISPLAY: ✨ Display ready for new content
I (16261) SENSOR: 📊 Reading sensor data from file: ./main/sensor.c, line: 18
I (16261) SENSOR: 🌡️  Temperature: 26.0°C
I (16261) SENSOR: 💧 Humidity: 64.9%
I (16261) DISPLAY: 📊 Data display from file: ./main/display.c, line: 21
I (16261) DISPLAY: 📈 Value 1: 30.50
I (16271) DISPLAY: 📉 Value 2: 65.00
I (16271) DISPLAY: 📢 Displaying from file: ./main/display.c, line: 15
I (16271) DISPLAY: 📺 Message: LED Status: ON
I (17221) LED: ❌ LED OFF from file: ./main/led.c, line: 27
I (17221) LED: 🔴 LED is now OFF
I (17221) LED: 🔄 LED toggled from file: ./main/led.c, line: 38
I (18271) MAIN: === Loop 5 ===
I (18271) DISPLAY: 🧹 Screen cleared from file: ./main/display.c, line: 28
I (18271) DISPLAY: ✨ Display ready for new content
I (18271) SENSOR: 📊 Reading sensor data from file: ./main/sensor.c, line: 18
I (18271) SENSOR: 🌡️  Temperature: 32.8°C
I (18271) SENSOR: 💧 Humidity: 96.6%
I (18271) DISPLAY: 📊 Data display from file: ./main/display.c, line: 21
I (18271) DISPLAY: 📈 Value 1: 31.50
I (18271) DISPLAY: 📉 Value 2: 66.00
I (18271) DISPLAY: 📢 Displaying from file: ./main/display.c, line: 15
I (18271) DISPLAY: 📺 Message: LED Status: OFF
I (18271) SENSOR: ✅ Sensor status check from file: ./main/sensor.c, line: 30
I (18271) SENSOR: 📈 All sensors operating normally
I (18281) DISPLAY: 📢 Displaying from file: ./main/display.c, line: 15
I (18281) DISPLAY: 📺 Message: Status Check Complete
I (20221) LED: ✅ LED ON from file: ./main/led.c, line: 20
I (20221) LED: 🟢 LED is now ON
I (20221) LED: 🔄 LED toggled from file: ./main/led.c, line: 38
I (20281) MAIN: === Loop 6 ===
I (20281) DISPLAY: 🧹 Screen cleared from file: ./main/display.c, line: 28
I (20281) DISPLAY: ✨ Display ready for new content
I (20281) SENSOR: 📊 Reading sensor data from file: ./main/sensor.c, line: 18
I (20281) SENSOR: 🌡️  Temperature: 27.7°C
I (20281) SENSOR: 💧 Humidity: 87.5%
I (20281) DISPLAY: 📊 Data display from file: ./main/display.c, line: 21
I (20281) DISPLAY: 📈 Value 1: 32.50
I (20281) DISPLAY: 📉 Value 2: 67.00
I (20281) DISPLAY: 📢 Displaying from file: ./main/display.c, line: 15
I (20281) DISPLAY: 📺 Message: LED Status: ON
```
## 🔍 คำถามทบทวน

1. **Multiple Source Files**: เหตุใดต้องแยก source code เป็นหลายไฟล์
Ans
    เพื่อให้ จัดระเบียบโค้ด ง่าย แยกตามหน้าที่ (modularity) เช่น sensor.c, led.c, main.c
    ดูแล/แก้ไข/ขยายระบบ สะดวก แก้แต่ละส่วนโดยไม่กระทบส่วนอื่น
    ช่วย ทำงานเป็นทีม ได้ดีขึ้น แต่ละคนดูแลไฟล์ของตัวเอง
    ลด conflict เมื่อ merge บน Git
    ช่วยให้ build เร็วขึ้น เพราะเปลี่ยนแค่บางไฟล์แล้วคอมไพล์แค่ไฟล์นั้น
   
2. **CMakeLists.txt Management**: การเพิ่มไฟล์ source ใหม่ต้องแก้ไขอะไรบ้าง?
Ans
```
set(SOURCES main.c led.c sensor.c) # เพิ่ม sensor.c ถ้ามีไฟล์ใหม่
```
ถ้าใช้ ESP-IDF/PlatformIO บางแบบอาจแค่เพิ่มไฟล์ใน src/ ก็พอ แต่กรณี project structure ปกติ ต้อง ระบุ source ใน CMakeLists.txt 

3. **Header Files**: บทบาทของไฟล์ .h คืออะไร และทำไมต้องมี?
Ans
บทบาท:
  ประกาศ function prototypes (เช่น void led_on(void);)
  ประกาศ structs, typedefs, enums, macro ที่ต้องใช้ข้ามไฟล์
  ทำหน้าที่เป็น "สัญญา" ว่าส่วนนี้มีฟังก์ชัน/ข้อมูลอะไรให้เรียกใช้
  
  เหตุผลที่ต้องมี:
  ช่วยให้ compiler รู้จัก สิ่งที่อยู่ในไฟล์อื่น
  ลดการ duplicate โค้ดในแต่ละไฟล์
  สนับสนุนการ แยก module ให้เรียกข้ามไฟล์ได้
  
4. **Include Directories**: เหตุใด CMakeLists.txt ต้องระบุ INCLUDE_DIRS?
Ans
  เพื่อบอก compiler ว่าจะหา header (.h) จาก path ไหน
  ถ้าไม่ระบุ path ที่ header อยู่ เวลาทำ #include "led.h" จะเจอ error ว่า "file not found"
  ป้องกันปัญหาเวลา header อยู่ต่าง directory เช่น
  ```
  include_directories(${PROJECT_SOURCE_DIR}/components/led/include)
  ```
5. **Git Ignore**: ไฟล์ .gitignore ช่วยอะไรในการจัดการ ESP32 project?
Ans
  ช่วยกันไม่ให้ไฟล์ขยะ/ไฟล์ build หรือ config เฉพาะเครื่อง (เช่น .vscode/, build/, .DS_Store) ถูกส่งขึ้น Git
  ป้องกันการ push ไฟล์ binary, ไฟล์ที่ generate อัตโนมัติ หรือไฟล์ sensitive (เช่น sdkconfig)
  ลดขนาด repo และลดปัญหา merge conflict จากไฟล์ที่ไม่ควร version control

6. **Task Management**: การใช้ FreeRTOS task ในโมดูล LED ช่วยอะไร?
Ans
    LED task ช่วยให้โค้ดควบคุม LED ทำงานแบบ async/parallel
    สามารถแยก logic การกระพริบ, การควบคุม, หรือรับ event จาก queue/interrupt ได้
    ทำให้โค้ด main ไม่ต้องคอยดูแล LED ตลอดเวลา
    ช่วยให้ระบบ responsive และ multitasking ได้ดีขึ้น

7. **Code Organization**: ข้อดีของการแยกโมดูล sensor, display, led เป็นไฟล์แยกคืออะไร?
Ans
    แยกความรับผิดชอบ (Separation of Concerns)
    ดูแล/ทดสอบ/แก้ไข แต่ละ module ได้อิสระ
    Reuse โมดูลใน project อื่นได้ง่าย
    ลด bug จากการแก้โค้ดข้าม module
    ขยายฟีเจอร์/เปลี่ยนแปลง เฉพาะส่วนได้ง่าย เช่น เปลี่ยน display แบบใหม่โดยไม่กระทบส่วน sensor หรือ led

## บันทึกผลการทดลอง
- ขั้นตอนที่ 1 (เฉพาะ sensor.c):
  จำนวนไฟล์ source: 2  
  ขนาด binary: 163273 bytes
  การทำงาน: โปรแกรมจำลองการอ่านข้อมูลจาก sensor โดยแสดงอุณหภูมิและความชื้นบน console พร้อมแสดงสถานะของ sensor ทุก 3 รอบ
- ขั้นตอนที่ 2 (เพิ่ม display.c):
  จำนวนไฟล์ source: 3
  ขนาด binary: 163981 bytes
  การทำงาน: เพิ่มการแสดงผลบนจอจำลองด้วย display_init(), display_show_message() และ display_show_data() เพื่อแสดงข้อความและค่าที่อ่านได้จาก sensor
- ขั้นตอนที่ 3 (เพิ่ม led.c):
  จำนวนไฟล์ source: 4
  ขนาด binary: 164873 bytes
  การทำงาน: เพิ่มการทำงานของ LED โดยรัน task ให้ LED กะพริบทุก 3 วินาที และแสดงสถานะ LED (ON หรือ OFF) บน display ทุกรอบ loop

## สังเกต:
- การเพิ่มไฟล์ source ส่งผลต่อขนาด binary อย่างไร?
  - **Ans:** เมื่อมีการเพิ่มไฟล์ source (.c) เช่น display.c และ led.c เข้าไปในโปรเจกต์ จะทำให้ขนาด binary เพิ่มขึ้นตามเนื้อหาที่เพิ่ม เช่น ฟังก์ชัน, ตัวแปร, และโค้ดที่ต้อง compile 
- LED กะพริบทุกกี่วินาที?
  - **Ans:** LED จะกะพริบ ทุก 3 วินาที
- แต่ละโมดูลแสดงข้อมูล file และ line อย่างไร?
  - **Ans:** โมดูลต่างๆ จะใช้ __FILE__ และ __LINE__ เพื่อแสดงข้อมูลชื่อไฟล์และบรรทัดในข้อความ Log ซึ่งช่วยให้สามารถติดตามได้ว่าข้อความ Log มาจากส่วนใดของโค้ด

