# tinyML4D-ml-kits
What machine learning kits are the best educational value for the lowest price and ease of use.


Around 2020 the [Arduino Tiny Machine Learning Kit](https://store-usa.arduino.cc/products/arduino-tiny-machine-learning-kit) for $60 USD or €50 was a Nano33BleSense with a OV7675 camera that coverred most of the beginner Machine Learning activities and even allowed using upto 18 different sensors that the board comes with. This kit was sent in groups of 10 to multiple Univsersities in Developing countries by both [TinyML4D](https://tinyml.seas.harvard.edu/) and [EdgeImpulse.com](https://www.edgeimpulse.com/)

Around 2022 that kit had components that were not available so the Nano33BleSense Rev2 was made with slightly different components which potentially has broken a few lessons.

The following code should help the transition from Rev1 to Rev2

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

As of July 2023 there are more powerful and low cost solutions for teaching Machine Learning, but are they better than the Arduino ML Kit?


This site has been made to explore that question and perhaps give some other options and why to choose those options.
















