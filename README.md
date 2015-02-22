# ChillHub

Welcome to the ChillHub getting started page. If you just purchased a ChillHub and are interested in getting it on your network and using any accessories you purchased then see [Start Here](#starthere). If you are ready to dive in and start creating new accessories see  [Developer Start Here](#developerstarthere). Contributions are highly encouraged. ChillHub is designed to be a platform for creating new accessories. 

A [note](#noteaboutsecurity) about security.

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
  - Contains the core [firmware] (https://github.com/FirstBuild/chillhub-firmware) for devices communicating to ChillHub and the Firebase cloud
  - Contains the wifi [commissioning] (https://github.com/FirstBuild/chillhub-commissioning) daemon 
  - Configuration information is stored in chillhub.json

+ Cloud
  - ChillHub communicates with a [Firebase](http://firebase.com) cloud for relaying information between devices and the cloud 
  - Any Firebase instance can be used and can be changed from the default FirstBuild instance 

+ FirstBuild Mobile app
  - A [framework](https://github.com/FirstBuild/FirstBuild-Mobile) for adding new screens for devices that you create
  - A wifi commissioning storyboard to connect ChillHub to a users home network
  - A main storyboard that utilizes RBStoryboard link for adding new storyboards
  - An authentication storyboard for logging in via Google+ or Facebook
  - A ChillHub storyboard with a MilkyWeigh accessory screen
  
+ Devices
  - ChillHub uses a protocol as outlined above in ChillHub computer to communicate with devices over USB. 
  - The [MilkyWeigh](https://github.com/FirstBuild/ChillHubMilkScaleCypress) device is a fully working example using a [Cypress board](http://www.cypress.com/?rID=92146)
  - Arduino Uno or any other USB Serial cable device can be used

## Security <a id="noteaboutsecurity"></a>

ChillHub is designed to be a developer platform and emphasis has been put on ease of developing new components. Basic safeguards have been put in place. Notes:

+ Communication to the Firebase cloud is encrypted with SSL
+ After logging in to Firebase the first time an authorization token from firebase is passed to the ChillHub via the mobile app. This token is good for 2 years. The token is only passed during the commissioning phase when the Mobile phone is directly connected to the ChillHub computer's wifi access point.
+ Device communications internally on the USB bus are not encrypted
+ ChillHub will only connect to WPA/WPA2 wifi access points
+ The linux operating system installed on ChillHub has not been "hardened" in order to enable the easy development. Developers are encouraged to secure their device in the way they prefer. Please see this great guide on raspberry pi [hardening] (http://automationguy.co.uk/home-lab/home-lab-build-part-13-raspberry-pi-hardening/)

