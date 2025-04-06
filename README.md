## General description
  The OpenBook E-Reader is an open-source e-reader device offering a distraction-free reading experience with physical buttons and a minimalist interface. It features environmental sensors that provide real-time environmental data, a sustainable design, and extended battery life of at least one week. The device boasts a large e-paper display, slim ergonomic design, and USB-C connectivity for charging and data transfer. OpenBook supports wireless ebook downloads and emphasizes customizable hardware and software for the tech-savvy reader. It aims to serve avid readers who value open-source technology, customization options, and environmental awareness.

## Block Diagram
![image-2](https://imgur.com/a/KbbQZAz)

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

## ESP32-C6 Pins

| ESP32-C6 Pin    | Component / Function  | Description and Reason for Use                                                                                                               |
|-----------------|-----------------------|----------------------------------------------------------------------------------------------------------------------------------------------|
| IO1 (SDA)     | I2C Bus               | Used for communication with the BME688 sensor, battery fuel gauge IC (MAX17048), and RTC (DS3231). I²C enables multiple devices on one bus. |
| IO2 (SCL)     | I2C Clock             | Provides the clock signal for the I²C bus, synchronizing data transfer between the ESP32-C6 and connected I²C devices.                      |
| IO5 (MISO)    | SPI (E-Paper)         | Master In Slave Out for the SPI interface with the E-Paper display; receives data from the display to the ESP32-C6.                         |
| IO6 (MOSI)    | SPI (E-Paper)         | Master Out Slave In for the SPI interface with the E-Paper display; sends data from the ESP32-C6 to the display.                            |
| IO7 (SCK)     | SPI Clock (E-Paper)   | Provides the clock signal for the SPI interface with the E-Paper display, synchronizing data transfer.                                      |
| IO8 (CS)      | Chip Select (E-Paper) | Selects the E-Paper display for SPI communication, allowing communication with a single SPI device at a time.                               |
| IO9           | E-Paper DC            | Data/Command control for the E-Paper display, indicating whether the transmitted data is command instructions or display data.              |
| IO10          | E-Paper RST           | Reset pin for the E-Paper display, used to initialize or reset the display.                                                                 |
| IO11          | E-Paper BUSY          | Busy status pin for the E-Paper display, indicating if the display is occupied and cannot receive new commands.                             |
| IO12          | BUTTON_BOOT           | Button to enter programming/bootload mode.                                                                                                  |
| IO13          | BUTTON_RESET          | Button for hardware reset of the ESP32-C6.                                                                                                  |
| IO14          | BUTTON_USER           | User-defined button for application interactions.                                                                                           |
| IO15          | MAX17048 ALERT        | Alert pin from the battery fuel gauge IC, signaling critical battery conditions.                                                            |
| GPIO16/TXD0   | USB D+                | Positive data line for the USB interface.                                                                                                   |
| GPIO17/RXD0   | USB D-                | Negative data line for the USB interface.                                                                                                   |
| IO18          | STATUS_LED            | Controls the status LED for visual indication of the device state.                                                                          |
| IO19          | SD Card CS            | Chip select for the SD card on the SPI interface.                                                                                           |
| IO20          | SD Card MISO          | Master In Slave Out for the SPI interface with the SD card; receives data from the SD card.                                                 |
| IO21          | SD Card MOSI          | Master Out Slave In for the SPI interface with the SD card; sends data to the SD card.                                                      |
| IO4           | SD Card CLK           | SPI clock for the SD card, synchronizing data transfer.                                                                                     |

###  Additional Details

  ####   I2C Interface
    The GPIO1 (SDA) and GPIO2 (SCL) pins are used for the I²C bus, connecting the ESP32-C6 to:
      - **BME688 Sensor:** For reading temperature, humidity, pressure, and air quality data.
      - **MAX17048:** For monitoring battery level.
      - **DS3231:** For real-time clock (RTC) functionality.
  
  ####   SPI Interface
    The GPIO5, GPIO6, GPIO7, and GPIO8 pins are dedicated to the SPI interface with the E-Paper display. This interface requires:
      - **MISO (GPIO5):** Receives data from the display.
      - **MOSI (GPIO6):** Transmits data to the display.
      - **SCK (GPIO7):** Synchronizes the data transfer.
      - **CS (GPIO8):** Selects the E-Paper display for communication.
  
  ####  User Buttons
    The GPIO12, GPIO13, and GPIO14 pins are connected to the user control buttons:
      - **GPIO12 (BUTTON_BOOT):** Enters programming/bootload mode.
      - **GPIO13 (BUTTON_RESET):** Resets the ESP32-C6.
      - **GPIO14 (BUTTON_USER):** Allows user-defined interactions.
  
  ####  USB
    GPIO16 and GPIO17 are used for the USB interface, facilitating data transfer and charging.
  
  ####  SD Card
    The GPIO19, GPIO20, GPIO21, and GPIO4 pins are used for the SPI interface with the SD card, enabling data storage and access.
