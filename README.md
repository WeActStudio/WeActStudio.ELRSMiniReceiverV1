* [中文版本](./README_zh.md)
# WeActStudio.ELRSMiniReceiverV1
![display](Images/1.png)

|Dir Name|Explain|
| :--:|:--:|
|Doc|DataSheet|
|Hardware|Hardware Development Kit|
|Firmwares|Firmware Binaries|

## Firmware Description
* Supports both receiver and transmitter firmware.  
* Receiver firmware filename: esp32c3_vx.x.x_rx_firmware_0x0000.bin  
* Transmitter firmware filename: esp32c3_vx.x.x_tx_firmware_0x0000.bin  

### Receiver firmware
* LED Indication Status https://www.expresslrs.org/quick-start/led-status/  
  |LED Indication|Status|
  | :--:|:--:|
  |Rainbow fade effect|Starting Up|
  |Green heartbeat|Web update mode enabled|
  |Orange Slow blink 500ms on/off|Waiting for connection from transmitter|
  |Red flashing 100ms on/off|Radio chip not detected|
  |Orange Double blink then pause|Binding mode enabled|
  |Orange Triple blink then pause|Connected to transmitter but mismatched model-match configuration|
  |Solid single color|Connected to a transmitter, color indicates packet rate|
  |No Light|Off or in Bootloader Mode|
* Button Description
  |Button|Description|
  | :--:|:--:|
  |Long Press|Enter Bind Mode -> Web Server Mode -> Reset|
  |Long Press and Power On|Enter Bootloader Mode|
* Enter Bind Mode  
  Method 1. Long press the button, wait for the LED to become orange double blink then pause status.  
  Method 2. Repeatedly power on the receiver 3 times, wait for the LED to become orange double blink then pause status.  



### Transmitter firmware
> CRSF UART baud rate adaptive, supports 400000, 115200, 5250000, 3750000, 1870000, 921600, 2250000.  
* LED Indication Status https://www.expresslrs.org/quick-start/led-status/  
  |LED Indication|Status|
  | :--:|:--:|
  |Blue heartbeat|Bluetooth joystick enabled|
  |Solid single color|Connected to receiver, color indicates packet rate|
  |Fading single color|No connection to receiver, color indicates packet rate|
  |One Orange flash every second|No handset connection|
  |Red flashing 100ms on/off|Radio chip not detected|
  |Rainbow fade effect|Starting Up|
  |Green heartbeat|Web update mode enabled|

## Pin Description
* Receiver Pinout：
  ```
  {
    "radio_busy": 3,
    "radio_dio1": 1,
    "radio_miso": 5,
    "radio_mosi": 4,
    "radio_nss": 7,
    "radio_sck": 6,
    "radio_dcdc": true,
    "power_min": 0,
    "power_high": 0,
    "power_max": 0,
    "power_default": 0,
    "power_control": 0,
    "power_values": [13],
    "power_lna_gain": 0,
    "pwm_outputs": [2,10,18,19,20,21],
    "button": 9,
    "led_rgb": 8,
    "led_rgb_isgrb": true,
    "vbat": 0,
    "vbat_offset": 12,
    "vbat_scale": 1180
  }
  ```
* Transmitter Pinout：
  ```
  {
    "radio_busy": 3,
    "radio_dio1": 1,
    "radio_miso": 5,
    "radio_mosi": 4,
    "radio_nss": 7,
    "radio_sck": 6,
    "radio_dcdc": true,
    "power_min": 0,
    "power_high": 0,
    "power_max": 0,
    "power_default": 0,
    "power_control": 0,
    "power_values": [13],
    "power_lna_gain": 0,
    "serial_rx": 20,
    "serial_tx": 21,
    "button": 9,
    "led_rgb": 8,
    "led_rgb_isgrb": true
  }
  ```
## VIN VBAT Circuit Description
> Input voltage: 0-36V  
![display](Hardware/VBAT%20VIN%20Circuit.png)

```
/*---------------------------------------
- WeAct Studio Official Link
- taobao: weactstudio.taobao.com
- aliexpress: weactstudio.aliexpress.com
- github: github.com/WeActStudio
- gitee: gitee.com/WeAct-TC
- blog: www.weact-tc.cn
---------------------------------------*/
```
