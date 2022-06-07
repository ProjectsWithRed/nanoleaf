# NanoLeaf

A modular NanoLeaf lights that not only allows you to make any NanoLeaf shape using as many or as little segments as you want, but you can also use the same identical modular segments to create a 4-digit display, which can be used to display the time, temperature, humidity, or pretty much anything you want!

There is a [video](https://youtu.be/RalzwaIh_J4) associated with this repository/project, I highly recommend watching it before using this repo.

[![Video](readme_imgs/thumbnail.png)](https://youtu.be/RalzwaIh_J4 "NanoLeaf video")

# Code for any custom NanoLeaf shape

You simply just need to go to [here](https://install.wled.me/), press install and follow the instructions.


# Code for the 4-digit display

Keep in mind, that you don't need to do any of the steps below if you are just creating a NanoLeaf shape. For the code for any NanoLeaf shape, see [Code for any custom NanoLeaf shape](#Code-for-any-custom-NanoLeaf-shape).

Please note, in the video (time: `13:37`) I go through and show the exact steps on how to upload and use the code for the 4-digit display. Below is just a short text version.


1. Install [VSCode](https://code.visualstudio.com/).
2. In VSCode, install the `PlatformIO IDE` extension.
3. Clone/download this repo.
4. Open the `/WLED` directory in VSCode.
5. There are two changes you need to make before uploading the code:
    - In `WLED/platformio.ini`, under the `[env:esp32dev]` environment, change the `upload_port` to your micro-controller port.
    - In `WLED/usermods/NanoLeaf_Display/usermod_nanoleaf_display.h`, change the `ADDR_LEDS_PER_SEG` variable to the number of addressable LED sections there are in your LED strip. Below is an illustration to explain this further. In the example below, there are 3 sections, since there are 2 cut marks, so if you were to cut the LED strip on the cut marks, you will get 3 seperate sections, this is the number you need to set the `ADDR_LEDS_PER_SEG` variable to.
    - ![LED strip sections](/readme_imgs/led_strip_sections.png)
6. Now you can upload the code.
7. For the setup you need to do on the phone and how to use the usermod settings to control the 4-digit display, refer to the video (time: `14:42`).


# Components

- [ESP32](https://www.amazon.co.uk/dp/B071P98VTG?ref_=cm_sw_r_cp_ud_dp_HRCFAE60FTX5CNG9CH61), for the micro-controller.
- [12V 8A](https://www.amazon.co.uk/dp/B0927KBGCP?ref_=cm_sw_r_cp_ud_dp_XS02N6BZ2QZ6SRK3ASNE), power supply.
- [LM2596](https://www.amazon.co.uk/dp/B077VW4BTY?ref_=cm_sw_r_cp_ud_dp_3PQZG5P3P4X3W8JCMQ5S) or any step down converter, to convert 12V to 5V for the ESP32. **Remember to use the screw on this component to adjust its output voltage to 5V using a voltmeter.**
- [LED strip](https://www.amazon.co.uk/dp/B01CNL6K52?ref_=cm_sw_r_cp_ud_dp_SHH2S3GJH9TY1MC4NM73), the specific one used in this project is the `WS2811` LED strip.
- 1000μF capacitor, across the LED strip.
- [A4 3mm matte opal acrylic sheets](https://plasticonline.co.uk/opal-frost-cast-acrylic-sheet.html) (x7), used to get the glowing effect. I recommend getting extra A4 sheets just in case something bad happens...
    - Refer to [Acrylic sheet shape](#Acrylic-sheet-shape) to see what shape you need to cut from the acrylic sheets.
- [DHT11](https://www.amazon.co.uk/dp/B06Y99X3NS?ref_=cm_sw_r_cp_ud_dp_4AR4MJQ16QP2X09JY0WM)(optional), used to get the temperature and humidity when using the 4-digit display.
- [Power switch](https://www.amazon.co.uk/dp/B01N2U8PK0?ref_=cm_sw_r_cp_ud_dp_JB40B1WS9YM9YZVZ7MQK), to turn on and off.
- M2 bolts, to attach the lid to the main housing part. They can be from 8mm to 12mm long.
- [20 AWG flexible silicon wires](https://www.amazon.co.uk/dp/B07G715HYY?ref_=cm_sw_r_cp_ud_dp_060MXTRE7K0QFSFT6WC1), for connecting segments together.
- [Dupont crimping tool](https://www.amazon.co.uk/dp/B07QNPZDTW?ref_=cm_sw_r_cp_ud_dp_D43ZQHCR3MZQAZ5CW36F), the tool used to make the dupont connectors.


# 3D models

Please refer to the `/3d_printing` directory.


# Acrylic sheet shape

To cut the acrylic to the correct shape, print this [A4 sheet](acrylic_sheet_reference.pdf). To ensure you have printed it to the correct scale, measure the top size of the shape, which should be `12 cm`.


# Wiring

## For any NanoLeaf shape
![nanoleaf shape wiring diagram](/readme_imgs/shape_wiring_dia.png)
![nanoleaf shape wiring image](/readme_imgs/shape_wiring_img.JPG)

## For the 4-digit display

![4-digit display wiring diagram](/readme_imgs/display_wiring_dia.png)
![4-digit display wiring image](/readme_imgs/display_wiring_img.JPG)

### 4-digit display segments wiring
![4-digit display segments wiring diagram](/readme_imgs/display_segments_wiring_dia.png)
![4-digit display segments wiring image](/readme_imgs/display_segments_wiring_img.JPG)
