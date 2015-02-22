# ChillHub

Welcome to the ChillHub getting started page. If you just purchased a ChillHub and are interested in getting it on your network and using any accessories you purchased then see [Start Here](#starthere). If you are ready to dive in and start creating new accessories see  [Developer Start Here](#developerstarthere). Contributions are highly encouraged. ChillHub is designed to be a platform for creating new accessories. 

## Start Here <a id="starthere"></a>

**ChillHub Unboxing**

After your refrigerator is unboxed, there are a few things you need to do. 

1. Place the ChillHub computer either on the top or back of your refrigerator. Double sided tape has been provided and will securely fasten the computer to the refrigerator. 
2. There are two USB cords coming out of the back of the refrigerator. Plug these into the ChillHub computer that you mounted on step 1. They are standard USB ports.
3. Plug the power adapter into the ChillHub computer. 
4. Plug in any accessories you have purchased.

**Connecting ChillHub**

In order to use ChillHub and its accesories you need to add it to your home wifi network.

**note:** _The FirstBuild iPhone app has been submitted to Apple and will be released pending their review. Please see alternative method [below](#connectingchillhubalternative) until the app is available._

1. ChillHub is shipped in an "off" state. Press and release the black button on the ChillHub computer to turn on ChillHub's wifi radio.
2. Download the FirstBuild iPhone app from the Apple app store.
3. Open the FirstBuild iPhone app. After signing in, click on the menu in the upper right corner and click "Add New Product". 
4. Follow the instructions for connecting the ChillHub to your home wifi.

**Alternative Connecting ChillHub <a id="connectingchillhubalternative"></a>**

1. ChillHub is shipped in an "off" state. Press and release the black button on the ChillHub computer to turn on ChillHub's wifi radio.
2. Follow the instructions for the ChillHub Commissioning process. [Manual Commissioning Process](https://github.com/FirstBuild/chillhub-commissioning)


## Developer Start Here <a id="developerstarthere"></a>

ChillHub is designed to be a developer platform for adding new devices! As such, every aspect of ChillHub is open source. This getting started document will walk you through the essentials.

**Architecture**

ChillHub consists of the following open components:

+ ChillHub Computer
  - Runs the linux operating system, the root password is the same as the WiFi password that is printed on the attached label.
  - Contains the core firmware for devices communicating to ChillHub and the Firebase cloud. [Firmware] (https://github.com/FirstBuild/chillhub-firmware)
  - Contains the wifi commissioning daemon [Commissioning] (https://github.com/FirstBuild/chillhub-commissioning)
  - Configuration information is stored in chillhub.json
+ Firebase
  - ChillHub communicates with a Firebase cloud for relaying information between devices and the cloud [Firebase](http://firebase.com)
  - Any Firebase instance can be used and can be changed from the default FirstBuild instance 

  
