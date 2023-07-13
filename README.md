# tinyML4D-ml-kits
What are the best educational value machine learning kits for the lowest price and ease of use?


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



| Board | cost USD | Image | Pros | Cons | Other |
| --- | --- | --- | --- | --- |--- |
| [Arduino Nicla Vision](https://store-usa.arduino.cc/products/nicla-vision) | $115 | <img src="https://github.com/hpssjellis/tinyML4D-ml-kits/assets/5605614/252f8d02-1d24-41b9-9579-232d5d456601" width=300 /> | Has all the basic Machine learning abilities of Motion, Sound and Vision, and all of those abilities are better and faster than the old Arduino ML kit. Also has a dual core similar to the PortentaH7 for more advanced processing. | High cost and fewer sensors than the Nano33BleSense | Other |
| [Seeedstudio XiaoEsp32S3](https://wiki.seeedstudio.com/xiao_esp32s3_getting_started/) | $13.99 | <img src="https://github.com/hpssjellis/tinyML4D-ml-kits/assets/5605614/70e75c60-aeb1-43d2-8fd8-171ca9a92e3d" width=300 /> | Has Vision and Sound with WiFI and BLE and an SD Card. Other senses can be inputed using the 10 pins. Very well built and efficiently programmed. The SD card is useful for simplifying data collection. WiFi abilities allows IOT connectivity | Less access to English speaking online help. The reset button is so small I had to 3D print a little clip to hold it down to put the board in DFU mode while plugging it in. | For any University that already has a robotics lab with sensors and actuators this in my opinion is the best board to get started on teaching Machine Learning in a classroom/lab setting |
| Board | cost USD | Image | Pros | Cons | Other |

<img src="https://github.com/hpssjellis/tinyML4D-ml-kits/assets/5605614/252f8d02-1d24-41b9-9579-232d5d456601" width=300 />
<img src="https://github.com/hpssjellis/tinyML4D-ml-kits/assets/5605614/70e75c60-aeb1-43d2-8fd8-171ca9a92e3d" width=300 />




![image](https://github.com/hpssjellis/tinyML4D-ml-kits/assets/5605614/252f8d02-1d24-41b9-9579-232d5d456601)


![image](https://github.com/hpssjellis/tinyML4D-ml-kits/assets/5605614/70e75c60-aeb1-43d2-8fd8-171ca9a92e3d)







