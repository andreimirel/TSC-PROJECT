# OpenBook E-Reader

## Descriere generală

**OpenBook** este un e-reader open-source, conceput pentru o experiență de lectură simplă, ecologică și fără distrageri. Proiectul se bazează pe microcontrolerul **ESP32-C6-WROOM-1-N8**, oferind conectivitate Wi-Fi 6, Bluetooth 5 și suport pentru senzori ambientali. Dispozitivul integrează un afișaj e-paper de 7,5 inci, senzor Bosch BME688, RTC cu backup, slot SD și sistem de gestionare a bateriei. Designul modular și consumul redus de energie îl fac ideal pentru utilizare portabilă.

---

## Diagramă bloc
![Diagramă bloc OpenBook](https://github.com/user-attachments/assets/ddbbfbfa-e72c-47d6-83a7-a39f880fc3e8)

---

## BOM (Bill of Materials)

| Componentă | Descriere | Link Mouser/Comet | Datasheet |
|------------|-----------|--------------------|-----------|
| ESP32-C6-WROOM-1-N8 | Microcontroler Wi-Fi 6/BLE | [Mouser](https://www.mouser.com/ProductDetail/Espressif-Systems/ESP32-C6-WROOM-1-N8) | [Datasheet](https://www.espressif.com/sites/default/files/documentation/esp32-c6-wroom-1_wroom-1u_datasheet_en.pdf) |
| BME688 | Senzor ambiental (T/H/P/VOC) | [Mouser](https://www.mouser.com/ProductDetail/Bosch-Sensortec/BME688) | [Datasheet](https://www.bosch-sensortec.com/media/boschsensortec/downloads/datasheets/bst-bme688-ds000.pdf) |
| DS3231SN# | RTC cu compensare termică | [Mouser](https://www.mouser.com/ProductDetail/Analog-Devices/DS3231SN) | [Datasheet](https://www.analog.com/media/en/technical-documentation/data-sheets/DS3231.pdf) |
| W25Q512JVEIQ | Memorie NOR Flash 64MB | [Mouser](https://www.mouser.com/ProductDetail/Winbond/W25Q512JVEIQ) | [Datasheet](https://www.winbond.com/resource-files/w25q512jv%20revf%2003272021%20plus.pdf) |
| USB4110-GF-A | Conector USB-C | [Mouser](https://www.mouser.com/ProductDetail/GCT/USB4110-GF-A) | [Datasheet](https://gct.co/files/drawings/usb4110.pdf) |
| MAX17048G+T10 | Fuel Gauge pentru baterie | [Mouser](https://www.mouser.com/ProductDetail/Analog-Devices/MAX17048G+T10) | [Datasheet](https://www.analog.com/media/en/technical-documentation/data-sheets/MAX17048-MAX17049.pdf) |
| MCP73831 | IC încărcare LiPo | [Mouser](https://www.mouser.com/ProductDetail/Microchip-Technology/MCP73831T-2ACI-OT) | [Datasheet](https://ww1.microchip.com/downloads/en/DeviceDoc/20001984G.pdf) |
| FH34SRJ-24S-0.5SH | Conector FPC pentru display | [Mouser](https://www.mouser.com/ProductDetail/Hirose-FH/FH34SRJ-24S-0.5SH) | [Datasheet](https://www.hirose.com/product/document?clcode=CL0537-0516-6-01&productname=FH34SRJ-24S-0.5SH(51)&series=FH34&documenttype=Catalog&lang=en&documentid=D31688_en) |
| CPH3225A | Supercondensator 3.3V | [Comet](https://www.comet.sri.ro/cautare?search=CPH3225A) | [Datasheet](https://www.seikocrystal.com/products/super-capacitor/pdf/CPH3225A.pdf) |
| SD0805S020S1R0 | Diodă Schottky | [Mouser](https://www.mouser.com/ProductDetail/KYOCERA-AVX/SD0805S020S1R0) | [Datasheet](https://datasheets.kyocera-avx.com/SD.pdf) |

---

## Funcționalitate Hardware

### Microcontroler ESP32-C6
- **Arhitectură:** RISC-V 32-bit, 160 MHz
- **Conectivitate:** Wi-Fi 6, Bluetooth 5, USB 2.0
- **Memorie:** 512KB SRAM + 8MB Flash extern
- **Interfețe:** SPI, I2C, UART, GPIO

### Afișaj E-Paper
- **Dimensiune:** 7.5 inci, 800x480 pixeli
- **Interfață:** 4-wire SPI (CS, DC, RST, BUSY)
- **Consum:** 0W în stare statică

### Senzor BME688
- **Măsurători:** Temperatură, umiditate, presiune, calitate aer (VOC)
- **Interfață:** I2C (adresă 0x77)

### Sistem de Alimentare
- **Baterie:** LiPo 2500mAh, 3.7V
- **Încărcare:** USB-C cu MCP73831 (1A)
- **Regulator:** LDO 3.3V (XC6220A331MR-G)
- **Protecție:** ESD pe linii USB și TVS diode.

### Slot SD Card
- **Interfață:** SPI (CS dedicat)
- **Capacitate:** Suportă carduri microSD până la 32GB.

---

## Conexiuni ESP32-C6

| Pin ESP32-C6 | Funcție | Componentă Conectată |
|--------------|---------|-----------------------|
| GPIO3       | SPI CS  | E-Paper Display       |
| GPIO4       | SPI CS  | W25Q512 Flash         |
| GPIO5       | SPI CS  | Slot SD Card          |
| GPIO6       | I2C SDA | BME688, DS3231, MAX17048 |
| GPIO7       | I2C SCL | BME688, DS3231, MAX17048 |
| GPIO8       | Buton Boot | Rezistor pull-down   |
| GPIO10      | UART TX | Debug/Programare      |
| GPIO11      | UART RX | Debug/Programare      |
| EN          | Enable  | Pull-up la 3.3V       |

---

## Specificații PCB
- **Dimensiuni:** 92mm x 54mm (2-layer)
- **Rutare:**
  - Trasee de alimentare: 0.3mm
  - Semnale: 0.15mm minim
  - Plan GND pe ambele straturi
  - **Antenă Wi-Fi:** Decupată sub modul, fără plan de masă.
- **Test Pads:** Marcate pe silkscreen (MISO, MOSI, 3V3, GND).

---

## Observații Design
- **Plasare Componente:**
  - ESP32 amplasat lângă margine pentru optimizare RF.
  - Butoane aliniate cu carcasa.
  - Decuplare: Condensatoare 100nF lângă fiecare IC.
- **DRC/ERC:** Verificat cu reguli din checklist-ul GitHub.
- **Licență:** Apache 2.0.

---

## Instrucțiuni
1. Clonează repository-ul.
2. Deschide fișierele `.sch` și `.brd` în Fusion 360.
3. Generează Gerber-uri și BOM folosind scripturile din `/Manufacturing`.
4. Asamblare PCB conform instrucțiunilor din `/Mechanical`.

---

## Probleme Întâlnite
- **Overlap Componente:** Rezolvat prin ajustarea footprint-ului bobinei.
- **DRC Errors:** Ignorate erorile de dimensiune pentru butoane și USB.
- **Antenă Wi-Fi:** Decupare PCB sub modul pentru reducerea interferențelor.

---

## Licență
Acest proiect este licențiat sub **Apache License 2.0**. Detalii în [LICENSE](LICENSE).
