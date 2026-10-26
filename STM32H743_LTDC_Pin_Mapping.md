# STM32H743IIT6 Core Board V1.5 - LTDC Pin Mapping
NICHT Vollständig!!!!!!
This list shows the hardware pin assignment between the 40-pin FFC/FPC display connector and the STM32H743IIT6 microcontroller MCU, verified via direct GPIO toggling.

## 1. Control & Timing Signals

| FPC Pin | STM32 Pin | LTDC Function | Description / Alternate Function |
|:-------:|:---------:|:--------------|:----------------------------------|
| 24      | PA8       | LTDC_CLK      | Pixel Clock (AF14)                |
| 33      | PF10      | LTDC_DE       | Data Enable (AF14)                |
| 31      | PI10      | LTDC_HSYNC    | Horizontal Sync (AF14)            |
| 32      | PI9       | LTDC_VSYNC    | Vertical Sync (AF14)              |

## 2. RGB Color Data Lines

### Red Channel (R2 - R7)

| FPC Pin | STM32 Pin | LTDC Function | Notes |
|:-------:|:---------:|:--------------|:------|
| 4       | PA2       | LTDC_R1       | (Often skipped in RGB565) |
| 5       | PH8       | LTDC_R2       | (Often skipped in RGB565) |
| 6       | PH9       | LTDC_R3       | **R-MSB 0** (RGB565 Bit 0) |
| 7       | PH10      | LTDC_R4       | **R-MSB 1** (RGB565 Bit 1) |
| 8       | PH11      | LTDC_R5       | **R-MSB 2** (RGB565 Bit 2) |
| 9       | PH12      | LTDC_R6       | **R-MSB 3** (RGB565 Bit 3) |
| 10      | PG6       | LTDC_R7       | **R-MSB 4** (RGB565 Bit 4 - Highest) |

### Green Channel (G2 - G7)

| FPC Pin | STM32 Pin | LTDC Function | Notes |
|:-------:|:---------:|:--------------|:------|
| 12      | PE5       | LTDC_G0       | (Often skipped in RGB565) |
| 13      | PE6       | LTDC_G1       | (Often skipped in RGB565) |
| 14      | PH13      | LTDC_G2       | **G-MSB 0** (RGB565 Bit 0) |
| 15      | PH14      | LTDC_G3       | **G-MSB 1** (RGB565 Bit 1) |
| 16      | PH15      | LTDC_G4       | **G-MSB 2** (RGB565 Bit 2) |
| 17      | PI0       | LTDC_G5       | **G-MSB 3** (RGB565 Bit 3) |
| 18      | PI1       | LTDC_G6       | **G-MSB 4** (RGB565 Bit 4) |
| 19      | PI2       | LTDC_G7       | **G-MSB 5** (RGB565 Bit 5 - Highest) |

### Blue Channel (B2 - B7)

| FPC Pin | STM32 Pin | LTDC Function | Notes |
|:-------:|:---------:|:--------------|:------|
| 21      | PG14      | LTDC_B0       | (Often skipped in RGB565) |
| 22      | PG12      | LTDC_B4       | *Attention:* Mapped as B4 in Hardware |
| 23      | PD6       | LTDC_B2       | **B-MSB 0** (RGB565 Bit 0) |
| 25      | PI4       | LTDC_B4       | (Alternative Pin / Hardware Check) |
| 26      | PI5       | LTDC_B5       | **B-MSB 3** (RGB565 Bit 3) |
| 27      | PI6       | LTDC_B6       | **B-MSB 4** (RGB565 Bit 4) |
| 28      | PI7       | LTDC_B7       | **B-MSB 5** (RGB565 Bit 5 - Highest) |

## 3. Power, Ground & Auxiliary Pins

| FPC Pin | STM32 Pin / Type | Function | Description / Usage |
|:-------:|:----------------:|:---------|:--------------------|
| 1       | PC1              | VLED- / NC| Often LED Cathode / Touch Interface |
| 2       | PC1              | VLED+ / NC| Often LED Anode (Backlight Power) |
| 3       | PG13             | RESET    | Display Hardware Reset |
| 11      | GND              | GND      | Ground |
| 20      | GND              | GND      | Ground |
| 29      | GND              | GND      | Ground |
| 30      | PG7              | LTDC_CLK | Alternative Clock Configuration Pin |
| 34      | PB14             | SRECL    | Often I2C SCL for Touch Controller |
| 35      | PB12             | INT      | Often Interrupt Pin for Touch Controller |
| 36      | PD13             | SDA      | Often I2C SDA for Touch Controller |
| 37      | PB13             | XR       | Resistive Touch X-Right / NC |
| 38      | PD12             | YD       | Resistive Touch Y-Down / NC |
| 39      | PH7              | XL       | Resistive Touch X-Left / NC |
| 40      | PD11             | YU       | Resistive Touch Y-Up / NC |
