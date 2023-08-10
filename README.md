# tinyML4D-ml-kits
What are the best educational value machine learning kits for the lowest price and ease of use?

Please post PR's to the site if you have any corrections or additions.


In 2021, the [Arduino Tiny Machine Learning Kit](https://store-usa.arduino.cc/products/arduino-tiny-machine-learning-kit) for $60 USD or €50 contained a Nano33BleSense with an OV7675 camera that covered most beginner Machine Learning activities. It even allowed using up to 18 different sensors that the board comes with. This kit was sent in groups of 10 to multiple universities in developing countries by both [TinyML4D](https://tinyml.seas.harvard.edu/) and [EdgeImpulse.com](https://www.edgeimpulse.com/).

In 2022, some components of that kit were not available, so the Nano33BleSense Rev2 was made with slightly different components, which potentially broke a few lessons. The following code should help the transition from Rev1 to Rev2:

```
// REV 2 CHANGES HERE 

/* For LSM9DS1 9-axis IMU sensor */
//#include <Arduino_LSM9DS1.h>     // REV 1
#include "Arduino_BMI270_BMM150.h" // REV 2

/* For HTS221 Temperature and humidity sensor */
//#include <Arduino_HTS221.h>     // REV 1
#include <Arduino_HS300x.h>       // REV 2
#define HTS HS300x                // For REV 2 to work with old REV1 code


// END REV 2 CHANGES  
```

The define  ```#define HTS HS300x``` allows old code to change all HTS to the new needed class HS300x which should allow old code to work with the REV2 changes.

As of July 2023, there are more powerful and low-cost solutions for teaching Machine Learning, but are they better than the Arduino ML Kit? This site has been made to explore that question and perhaps give some other options and why to choose those options.





------------------------------------------

Disclaimer: I am Jeremy Ellis (@rocksetta, jerTeach, hpssjellis) and I am biased towards my own course [maker100](https://github.com/hpssjellis/maker100), which uses both the Arduino PortentaH7 with LoRa vision shield (and the ethernet vision shield) to teach high school students in a hands-on, minimal lecture environment, teaching Robotics with sensors, actuators, IOT and Machine Learning.

--------------------



# TimyML4D Machine Learning Kit Suggestions

| Board | Cost USD add Customs and Shipping | Image | Pros | Cons | Other |
| --- | --- | --- | --- | --- |--- |
| <a name="01" href="#01">`01`</a> [Arduino ML Kit](https://store-usa.arduino.cc/products/arduino-tiny-machine-learning-kit) | $60 | <img title="Arduino ML Kit" src="https://github.com/hpssjellis/tinyML4D-ml-kits/assets/5605614/0d974b37-8f75-4d56-aa5d-97a31096e4ba" width=300 /> | Everything you need to get started: vision, Sound, Motion and up to 18 Senses, also has BLE for some IOT connectivity | Rev2 code is different than Rev1 and the Camera Resolution processing abilities are not as powerful as some modern boards. No WiFi, this is a big issue for the potential IOT component of Machine Learning | - |
|<a name="02" href="#02">`02`</a> [Arduino Nicla Vision](https://store-usa.arduino.cc/products/nicla-vision) | $115 | <img title="Arduino Nicla Vision" src="https://github.com/hpssjellis/tinyML4D-ml-kits/assets/5605614/252f8d02-1d24-41b9-9579-232d5d456601" width=300 /> | Has all the basic Machine learning abilities of Motion, Sound and Vision, Time Of Flight (proximity), WiFi/Ble and all of those abilities are better and faster than the old Arduino ML kit. Also has a dual core similar to the PortentaH7 for more advanced processing. | High cost and fewer sensors than the Nano33BleSense. No SD card to simplify data collection | For any University that already has a robotics lab with sensors and actuators this, in my opinion, is the best edgeimpulse fully supported board with Arduino Multilanguage support. By having Vision, Sound and Motion on the same board it makes getting started with ML very easy.  |
|<a name="03" href="#03">`03`</a> [Seeedstudio XiaoEsp32S3](https://wiki.seeedstudio.com/xiao_esp32s3_getting_started/) | $13.99 | <img title="Seeedstudio XiaoEsp32S3" src="https://github.com/hpssjellis/tinyML4D-ml-kits/assets/5605614/8322f5fa-be96-4568-af08-f022c245b735" width=300 /> | Has Vision (1600px x 1200px) and Sound with WiFI and BLE and an SD Card. Other senses can be inputed using the 10 pins. Very well built and efficiently programmed. The SD card is useful for simplifying data collection. WiFi/BLE abilities allows IOT connectivity | Less access to English speaking online help. No onboard IMU for motion analysis. The reset button is so small I had to 3D print a little clip to hold it down to put the board in DFU mode while plugging it in. <br><img  title="3DPrinted-Reset-button-Clip"  src="https://github.com/hpssjellis/tinyML4D-ml-kits/assets/5605614/6fcfece4-4996-4c15-a4bf-3f6db4e998d8" width=50 /><br> see file ```XIAO-esp32s3-pin-hold01-v04 (1).stl``` | For any University that already has a robotics lab with sensors and actuators this, in my opinion, is the best board to get started on teaching Machine Learning in a classroom/lab setting |
|<a name="04" href="#04">`04`</a> [Seeedstudio XiaoEsp32S3](https://wiki.seeedstudio.com/xiao_esp32s3_getting_started/) with [Grove Starter Kit](https://www.seeedstudio.com/Seeed-XIAO-Starter-Kit-p-5378.html) | $13.99 + $49.00 = $62.99 | <img  title="Seeedstudio XiaoEsp32S3"  src="https://github.com/hpssjellis/tinyML4D-ml-kits/assets/5605614/8322f5fa-be96-4568-af08-f022c245b735" width=300 /> <img title="Grove Starter Kit" src="https://github.com/hpssjellis/tinyML4D-ml-kits/assets/5605614/ec64b824-19b5-45e1-9391-6949646b7628" width=300 /> | Now has the power of a new board with sensor connectivity of the Grove system | Now slightly more expensive than the original Arduino ML kit. Less access to English speaking online help although the Grove system is sold by Arduino and as such should have some online support from Arduino. The Expansion board solves the small reset button issue | This board comes with 8MB ram allowing it a lot of power compared to some other boards. The grove system is also sold by Arduino, allowing many more sensors. The board can also be removed from the expansion board and put on a regular breadboard. In my opinion this is a very good starting system for a group without an existing robotics lab. Lots of help from Marcelo Rovai [here](https://github.com/Mjrovai/XIAO-ESP32S3-Sense) or Jeremy Ellis [here](https://github.com/hpssjellis/mcu-stable-edu-launch/tree/main/xiao-esp32s3). Note: the very cheap base $7 USD XiaoEsp32S3 base board can directly be placed in products for wearables etc.|
|<a name="05" href="#05">`05`</a> my [Maker100](https://github.com/hpssjellis/maker100/blob/main/price-list-2024.md) | $500.00 + a robotics lab at about $5000 |  <img  title="Jeremy Ellis Maker100"  src="https://github.com/hpssjellis/tinyML4D-ml-kits/assets/5605614/11863c7a-da58-41c1-85b9-8cbfa0893fa1" width=300 /> | Pro: A complete set of Robotics, sensors, actuators, IOT and Machine Learning | Con: The large cost per student or cost per small groups of students | This course [maker100](https://github.com/hpssjellis/maker100) looks at multiple uses for Machine Learning and uses hands on methods to show students what is possible|
|<a name="06" href="#06">`06`</a> [rp2040 pico WH](https://thepihut.com/products/raspberry-pi-pico-w?src=raspberrypi&variant=41952994787523) | ~$9.28 USD | <img  title="Raspberry Pi rp2040 pico WH"  src="https://github.com/hpssjellis/tinyML4D-ml-kits/assets/5605614/916c32c9-1ad9-4a63-9c31-6799b480a379" width=300 /> | Pro: Cost, WiFi and headers | Con: No ML Sensors |  |
|<a name="07" href="#07">`07`</a> [Bosch Arduino / Nicla Sense ME](https://store-usa.arduino.cc/products/nicla-sense-me) | $82 USD | <img  title="Nicla Sense ME"  src="https://github.com/hpssjellis/tinyML4D-ml-kits/assets/5605614/182b7196-edea-416b-8e21-6473165e7d6e" width=300 />  | Multi-sensor with IMU 4 gas sensors | No Camera, WiFi or Microphone| Better to spend a bit more and get the Nicla Vision, unless you really need the gas sensors. Also the Nicla Voice is with IMU and Sound |
|<a name="08" href="#08">`08`</a> [Arducam pico4ML](https://www.uctronics.com/-rp2040-based-arducam-pico4ml-dev-board-for-machine-vision.html) | $25 | <img  title="Arducam pico4ML"  src="https://github.com/hpssjellis/tinyML4D-ml-kits/assets/5605614/f1e31078-97ab-40a0-826b-b87a94bf9356" width=100 /> | Pro: Has camera, IMU, microphone and LCD on the board | Con: No WiFi or BLE and I could never get it working with the Arduino IDE. I havn't tried it in a while | Great price |
|<a name="09" href="#09">`09`</a> [Sony Spresense main, extension board and camera](https://www.mouser.ca/new/sony-spresense/) | 55+35+35 = $125.00 |  <img  title="Sony Spresense"  src="https://github.com/hpssjellis/tinyML4D-ml-kits/assets/5605614/d2199435-88d3-4a5d-9581-a8e49dd37379" width=100 />  | Pro: Camera and microphone well made package | Con: Missing IMU and WiFi/BLE| Really well made board. I had some problems getting machine learning code working. An Engineer would be fine with it |
|<a name="10" href="#10">`10`</a> [Renesas ML Kit](https://www.renesas.com/us/en/products/microcontrollers-microprocessors/ra-cortex-m-mcus) |  |  |  | |  |
|<a name="11" href="#11">`11`</a> [NXP ML Kit](https://www.nxp.com/) |  |  |  | |  |
|<a name="12" href="#12">`12`</a> [ST ML Kit](https://www.st.com/en/microcontrollers-microprocessors.html) |  |  |  | |  |
|<a name="13" href="#13">`13`</a> [Syntiant ML Kit](https://www.syntiant.com/tinyml) |  |  |  | |  |
|<a name="14" href="#14">`14`</a> [Wio Terminal ML kit](https://www.seeedstudio.com/Wio-Terminal-Getting-Started-with-TinyML-Kit-p-5324.html) | $5.90 | - | Has microphone and a few other sensors | No Wifi, Camera, IMU | Tutorial at [Wio-Terminal-TinyML-Kit-Course]https://wiki.seeedstudio.com/Wio-Terminal-TinyML-Kit-Course/) |
|<a name="15" href="#15">`15`</a> Board | cost USD | Image | Pros | Cons | Other |




.


.



.

.




.


