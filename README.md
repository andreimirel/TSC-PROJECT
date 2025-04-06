## Core Hardware Modules

### 1. Processing Unit
- **ESP32-C6-WROOM-1-N8**  
  - **Key Features**:
    - 160MHz RISC-V single-core processor
    - 512KB SRAM + 8MB external flash
    - Wi-Fi 6 (802.11ax) and Bluetooth 5 LE
    - Ultra-low-power modes (<5µA deep sleep)
  - **Functions**:
    - Manages all peripheral communication
    - Handles e-book rendering and UI operations
    - Processes environmental sensor data
    - Manages power states and battery charging

### 2. Display System
- **7.5" E-Paper Display (WSH-13187)**
  - **Specifications**:
    - 800×480 resolution, 8:1 contrast ratio
    - SPI interface (4-wire) @ 10MHz max
    - Partial refresh (<0.5s), full refresh (<1s)
    - 170° viewing angle
  - **Power Management**:
    - 0W power consumption when static
    - 120mW during refresh (active)

### 3. Environmental Sensing
- **BME688 Integrated Sensor**
  - **Measurement Capabilities**:
    - Temperature: ±1°C accuracy (0-65°C)
    - Humidity: ±3% RH (20-80% RH)
    - Pressure: ±1 hPa (300-1100 hPa)
    - Air Quality: VOC and eCO2 detection
  - **Interface**:
    - I2C @ 400kHz
    - 30s warm-up time for accurate readings
  - **Power Consumption**:
    - 2mA during active measurement
    - 0.5µA in sleep mode

### 4. Power Management System
| Component | Function | Specifications |
|-----------|----------|----------------|
| **2500mAh LiPo Battery** | Primary power source | 3.7V nominal, 2C discharge rate |
| **MCP73831** | Battery charging | 500mA max charge current, 4.2V regulation |
| **MAX17048** | Fuel gauge | ±1% voltage accuracy, I2C interface |
| **XC6220A331MR-G** | Voltage regulator | 3.3V @ 300mA, 50µA quiescent current |

### 5. User Interface Components
- **Tactile Buttons (3x)**
  - Panasonic EVQ-Q2A03W switches
  - 1M cycle lifespan
  - Hardware-debounced (RC filters)
- **LED Indicators**:
  - Charging status (red/green)
  - System activity (blue)

### 6. Connectivity
- **USB-C Port (Amphenol 12401641E4R)**
  - USB 2.0 Full Speed (12Mbps)
  - 5V/1A charging
  - ESD protection (USBLC6-2SC6Y)
- **Wi-Fi 6**:
  - 20MHz channel bandwidth
  - WPA3 security support
  - OTA update capability

### 7. Memory & Storage
| Component | Type | Capacity | Interface |
|-----------|------|----------|-----------|
| **W25Q512JVEIQ** | SPI Flash | 512Mb (64MB) | Quad-SPI @ 133MHz |
| **MicroSD Slot** | Expandable | Up to 1TB | SPI @ 25MHz |


## Bill of Materials

| Qty | Value | Description | Manufacturer Part # | Mouser Link |
|-----|-------|-------------|----------------------|-------------|
| 1 | - | ESP32-C6 Module | ESP32-C6-WROOM-1-N8 | [Datasheet](https://www.mouser.co.uk/datasheet/2/891/Espressif_ESP32_C6_WROOM_1__Datasheet_V0_1_PRELIMI-3239987.pdf) |
| 1 | - | Environmental Sensor | BME688 | [Datasheet](https://www.mouser.co.uk/datasheet/2/783/bst_bme688_fl000-2307034.pdf) |
| 1 | - | Real Time Clock | DS3231SN# | [Datasheet](https://www.mouser.co.uk/datasheet/2/609/DS3231-3421123.pdf) |
| 1 | - | MicroSD Card Socket | 112A-TAAR-R03 ATTEND | [Datasheet](https://www.attend.com.tw/data/download/file/112A-TAAR-R03.rar) |
| 1 | - | USB Type-C Connector | USB4110-GF-A | [Datasheet](https://www.mouser.co.uk/datasheet/2/837/GCT_USB4110_Product_Drawing___20k_cycles-3455479.pdf) |
| 1 | - | FFC Connector | FH34SRJ-24S-0.5SH | [Datasheet](https://www.mouser.co.uk/datasheet/2/185/FH34SRJ_24S_0_5SH_99__CL0580_1255_6_99_2DDrawing_0-1615044.pdf) |
| 1 | - | Qwiic Connector | QWIIC_RIGHT_ANGLE | [Datasheet](https://www.mouser.co.uk/datasheet/2/813/Qwiic_Connector_Datasheet-1223982.pdf) |
| 1 | - | Li-Ion Charge Controller | MCP73831 | [Datasheet](https://www.mouser.co.uk/datasheet/2/268/MCP73831_Family_Data_Sheet_DS20001984H-3441711.pdf) |
| 1 | - | LDO Regulator | XC6220A331MR-G | [Datasheet](https://www.mouser.co.uk/datasheet/2/760/xc6220-3371556.pdf) |
| 1 | - | Fuel Gauge IC | MAX17048G+T10 | [Datasheet](https://www.mouser.co.uk/datasheet/2/609/MAX17048_MAX17049-3469099.pdf) |
| 1 | - | Voltage Detector | BD5229G-TR | [Datasheet](https://fscdn.rohm.com/en/products/databook/datasheet/ic/power/voltage_detector/bd52xxg-e.pdf) |
| 2 | 20V/4.2A | P-Channel MOSFET | DMG2305UX-7 | [Datasheet](https://www.diodes.com/assets/Datasheets/DMG2305UX.pdf) |
| 1 | - | N-Channel MOSFET | SI1308EDL-T1-GE3 | [Datasheet](https://www.vishay.com/doc?63399) |
| 15 | 10kΩ | Resistor | RR0402 | [Datasheet](https://www.mouser.com/ds/2/447/PYu-RC0402_51_RoHS_L_6_r-8721.pdf) |
| 8 | 100nF | Capacitor | CC0402 | [Datasheet](https://eu.mouser.com/datasheet/2/40/cx5r_KGM-3223198.pdf) |
| 10 | 1µF/50V | Capacitor | CC0402 | [Datasheet](https://eu.mouser.com/datasheet/2/40/cx5r_KGM-3223198.pdf) |
| 5 | 4.7µF | Capacitor | CC0402 | [Datasheet](https://eu.mouser.com/datasheet/2/40/cx5r_KGM-3223198.pdf) |
| 3 | - | Schottky Diode | MBR0530 | [Datasheet](https://www.onsemi.com/PowerSolutions/product.do?id=MBR0530T3G) |
| 6 | - | TVS Diode | PGB1010603MR | [Datasheet](https://www.littelfuse.com/assetdocs/pulseguard-esd-suppressors-pgb1-datasheet?assetguid=8a337998-d54d-466b-be4e-dc5bcd1f9321) |
| 1 | 100µF | Polarized Capacitor | CPOL-EUCT3528 | [Datasheet](https://www.mouser.co.uk/datasheet/2/396/mlcc02_e-1307760.pdf) |
| 1 | - | Inductor | 744043680 | [Datasheet](https://www.we-online.com/components/products/datasheet/744043680.pdf) |
| 1 | - | ESD Protection Diode | USBLC6-2SC6Y | [Datasheet](https://www.mouser.co.uk/datasheet/2/389/usblc6_2sc6y-1852505.pdf) |
| 2 | - | Schottky Diode | SD0805S020S1R0 | [Datasheet](https://www.mouser.co.uk/datasheet/2/40/schottky-3165252.pdf) |
| 1 | - | Supercapacitor | CPH3225A | [Datasheet](https://www.mouser.co.uk/datasheet/2/360/Seiko_Instruments_MicroBattery_E_20230330_2024Jan_-3561061.pdf) |
| 1 | - | Varistor | ESP32C6_VARISTOR_CT | [Datasheet](https://www.mouser.co.uk/datasheet/2/358/typ_PFMF-1275918.pdf) |
| 17 | - | Test Points | TPTP20R | [Datasheet](https://www.mouser.co.uk/datasheet/2/215/5265_5269-2935484.pdf) |
| 1 | - | Solder Jumper | SJ | [Datasheet](https://www.mouser.co.uk/datasheet/2/210/ASC_WR-3314721.pdf) |
| 1 | - | LED (Green) | ADAFRUIT_LEDCHIP-LED0603 | [Specs](https://www.3dcontentcentral.com/secure/download-model.aspx?catalogid=9481&id=681976) |
| 3 | - | Custom Buttons | BUTTON_CUSYOMV1 | - |
