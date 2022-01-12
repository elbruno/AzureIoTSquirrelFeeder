# Using AzureIoT to feed my squirrels 🐿️ with a WioTerminal

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](/LICENSE)
[![Twitter: elbruno](https://img.shields.io/twitter/follow/elbruno.svg?style=social)](https://twitter.com/kartben)
[![PlatformIO CI](https://github.com/kartben/wioterminal-azureiothub-sample/workflows/PlatformIO%20CI/badge.svg)](https://github.com/elbruno/AzureIoTSquirrelFeeder/actions?query=workflow%3A%22PlatformIO+CI%22)

During the last couple of months, I’ve having fun with my new friends at home: 🐿️🐿️🐿️. These little ones, are extremelly funny, and they literally don’t care about the cold 🥶❄️☃️.

[<img src="img/squirrell-on-the-snow.png" width="350"/>](squirrell-on-the-snow.png)

So, I decided to help them and build an Automatic Feeder using Azure IoT, a Wio Terminal and maybe some more devices. 

As the Wio Terminal is one of PlatformIO's (many!) supported platforms, the sample is conveniently made available as a PlatformIO project. This means that you don't have to worry about installing the [multiple Arduino libraries](https://wiki.seeedstudio.com/Wio-Terminal-Network-Overview/) the Wio Terminal requires for Wi-Fi & TLS, and you don't need to manually install any other third-party library either! All dependencies are automatically fetched from Github by the PlatformIO Library Manager.

## Required Hardware

The main components for this project are from [SeeedStudio](https://www.seeedstudio.com/). In this version we use popular and easy to use components.

- [Wio Terminal](https://www.seeedstudio.com/wio-terminal)
- [Ultrasonic Range Detector](https://www.seeedstudio.com/Grove-Ultrasonic-Distance-Sensor.html)
- [Servo Motor](https://www.seeedstudio.com/Grove-Servo.html)

Why [Grove Sensors and Actuators](https://www.seeedstudio.com/category/Grove-c-1003.html)?, to avoid dealing with wires and soldering. Grove is an open-source, modulated, and ready-to-use toolset. Grove simplifies the learning process significantly.

Go build the feeder I bought a $2 bird feeder, and I created a funnel with a lid to deliver the nuts for the squirrels. It was a DIY project, and in near iterations and I may think on a complete design for 3D printers.

Here is the feeder in action: 

<img src="img/Wio Feeder-Buttons.gif" width="350"/>

## Running the Sample

The code for the Wio Terminal, is based on the samples from 

### [IoT for Beginners](https://aka.ms/iot-beginners)

If you want to learn from zero how to create a complete solution for Azure IoT, I strongly advice you to follow the tutorial. (Bonus: it’s super fun!).

The code for the current solution is available in the [src] folder. Just need to complete the information in the [config.h] file and your solution will be up and running!

```c++
// WiFi credentials
const char *SSID = "";
const char *PASSWORD = "";

// IoT Device credentials
const char *CONNECTION_STRING = "";
```

Use the [PlatformIO IDE](https://marketplace.visualstudio.com/items?itemName=platformio.platformio-ide) (VS Code extension) or the [PlatformIO command-line interface](https://platformio.org/install/cli) to deploy the application to your Wio Terminal. 

## Testing the sample

Once the Ultrasonic Range Detector Sensor and the servo motor are connected to the device, we can start the Detection process. When an animal is detected, the lid will be opened, and a telemetry message will be sent to Azure IoT. 

After 3 seconds, the lid will be close, and a telemetry message will be sent to Azure IoT. 

<img src="img/Wio-Feeder-Demo-Azure-Iot-Telemetry.gif" width="650"/>


You can use the [Azure IoT Explorer](https://github.com/Azure/azure-iot-explorer/releases) to test that your Wio Terminal is properly connected to Azure IoT Hub, i.e that it is regularly sending telemetry data, and responding to commands.

## Additional Resources

You can check a session recording about this topic in English and Spanish.

- Eng - [Using Azure IoT to feed my squirrels 🐿️](https://aka.ms/IoTtoFeedSquirrels)
- Spa - [Utilizando Azure IoT para darle de comer a mis ardillas 🐿️](https://aka.ms/ReactorSession1.6)

In my personal blog "[ElBruno.com](https://elbruno.com)", I wrote about several scenarios on how to work and code for the Wio Terminal. These links may help to understand specific implementations of the sample code:

- [WioTerminal – Working with servos 🦾](https://elbruno.com/2021/12/13/wioterminal-working-with-servos-%f0%9f%a6%be-code-and-platformio_org/)
- [WioTerminal – Connecting to Wifi 📶, online information in TFT 📺](https://elbruno.com/2021/12/10/wioterminal-connecting-to-wifi-%f0%9f%93%b6-online-information-in-tft-%f0%9f%93%ba-code-and-platformio_org/)
- [WioTerminal – Display a countdown progress bar 🚥](https://elbruno.com/2021/11/03/wioterminal-display-a-countdown-progress-bar-%f0%9f%9a%a5-for-the-next-azureiot-%e2%98%81%ef%b8%8f-refresh-data/)
- [WioTerminal – Display a Door 🚪 state using XBitmap](https://elbruno.com/2021/11/01/wioterminal-display-a-digitaltwin-door-%f0%9f%9a%aa-state-using-xbitmal-with-azureiot-%e2%98%81%ef%b8%8f/)
- [WioTerminal – Buttons and Charts time 📊📉📊](https://elbruno.com/2021/10/19/wioterminal-buttons-and-charts-time-%f0%9f%93%8a%f0%9f%93%89%f0%9f%93%8a/)


## Author

👤 **Bruno Capuano**

* Website: https://elbruno.com
* Twitter: [@elbruno](https://twitter.com/elbruno)
* Github: [@elbruno](https://github.com/elbruno)
* LinkedIn: [@elbruno](https://linkedin.com/in/elbruno)

## 🤝 Contributing

Contributions, issues and feature requests are welcome!

Feel free to check [issues page](https://github.com/elbruno/AzureIoTSquirrelFeeder/issues).

## Show your support

Give a ⭐️ if this project helped you!


## 📝 License

Copyright &copy; 2021 [Bruno Capuano](https://github.com/elbruno).

This project is [MIT](/LICENSE) licensed.

***