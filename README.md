# NodeSmartHome
NodeSmartHome is a project for integrating smart devices in your home using NodeMCU, an ESP8266-based microcontroller board. With NodifyHome, you can control and automate various smart devices such as lights, switches, thermostats, and sensors, and integrate them into a single smart home system that can be controlled from anywhere.

### Software Requirements

* Arduino IDE (Version- 1.8.29)
* NodeMCU integration to Arduino IDE (Version- 2.7.3)
* MIT AI2 Companion Android App from Google Playstore

### Hardware Requirements

* NodeMCU ESP8266 Wifi Module
* Relay Module (Optional)
* 4 Loads (LED Bulbs in this case)
* Jumpers

# Steps to set up the project:

* ## Installation of Arduino IDE 
#### 1. Go to https://www.arduino.cc/

![image](https://github.com/SaxenaAnushka102/NodeSmartHome/assets/58849657/8c96b6b8-85a1-416a-8452-fa6e14934238)

#### 2. Click on `Software` tab.

![image](https://github.com/SaxenaAnushka102/NodeSmartHome/assets/58849657/969acddd-197d-44df-9501-064e29593213)

#### 3. Scroll down to Downloads.

![image](https://github.com/SaxenaAnushka102/NodeSmartHome/assets/58849657/2898eff9-ba1e-4f28-9faa-62857ca9e299)

#### 4. Download the .exe file according to your Operatng System. I have got "Windows 10 and newer, 64 bits" for my system.

![image](https://github.com/SaxenaAnushka102/NodeSmartHome/assets/58849657/2dd5605f-ef29-4d43-9e16-f1a053496697)

* ### ESP8266 add-on in Arduino IDE
#### 1. Go to the Arduino IDE and on the tabs listed on the top ribbon, click on `File` > `Preferences`.
![image](https://github.com/SaxenaAnushka102/NodeSmartHome/assets/58849657/fb444b2f-1058-42a7-8ae2-9bad63c9feb3)

#### 2. Enter https://arduino.esp8266.com/stable/package_esp8266com_index.json into the "Additional boards Manager URLs" field as shown below & click OK.

![image](https://github.com/SaxenaAnushka102/NodeSmartHome/assets/58849657/48f95f02-2263-4146-a1b7-14eb9eab5383)

#### 3. Go to `Tools` > `Boards` > `Boards Manager...`

![image](https://github.com/SaxenaAnushka102/NodeSmartHome/assets/58849657/67e0673f-b834-4ccd-ba23-93a2b9a3d445)

#### 4. Search for ESP8266 and install version 2.7.3

![image](https://github.com/SaxenaAnushka102/NodeSmartHome/assets/58849657/eb796acf-1a08-4787-866a-f490493ee47e)


* ## Installation of Firebase Library 

#### 1. Go to https://github.com/FirebaseExtended/firebase-arduino

![image](https://github.com/SaxenaAnushka102/NodeSmartHome/assets/58849657/bcc45717-99b4-430e-9085-29e73a6529a5)

#### 2. In the Repository, click on `Code` then click on `Download ZIP`

![image](https://github.com/SaxenaAnushka102/NodeSmartHome/assets/58849657/f20e3d8e-4e61-429f-9abe-9a774e9138f1)

#### 3. In Arduino IDE click on the `Sketch` tab listed on the top ribbon, click on `Include Library` > `Add .ZIP Library...`

![image](https://github.com/SaxenaAnushka102/NodeSmartHome/assets/58849657/a1169b62-5bf1-468c-adf6-81b2c2b5166a)

#### 4. Go to the ZIP folder you just downloaded, Select & click Open

![image](https://github.com/SaxenaAnushka102/NodeSmartHome/assets/58849657/3122505f-2bad-4299-a389-2328826000b6)

FirebaseArduino now depends on ArduinoJson library


* ## Installation of Arduino Json Library(version-5.13.2)

#### 1. In Arduino IDE click on the Sketch tab listed on the top ribbon, click on `Include Library` > `Manage Library`

![image](https://github.com/SaxenaAnushka102/NodeSmartHome/assets/58849657/5c9faef4-6a0f-4394-9497-5d17dfcddcde)

#### 2. Search for ArduinoJson by Benoit and install version 5.13.2

![image](https://github.com/SaxenaAnushka102/NodeSmartHome/assets/58849657/6cc499eb-4d5e-4eb1-bff0-5fa18ca5e70c)


* ## Firebase Account Creation and setting up the project

#### 1. Go to https://firebase.google.com/

![image](https://github.com/SaxenaAnushka102/NodeSmartHome/assets/58849657/fcf0ba8c-4167-43c0-88af-d122edd1f5fb)

#### 3. Choose Default Account on Firbase & click on `Create Project`.

![image](https://github.com/SaxenaAnushka102/NodeSmartHome/assets/58849657/38860844-1fd5-4ca1-a72f-28b405854bf6)

#### 4. From the left nav bar, go to `Build` > `Realtime Database` > `Create Database`

![image](https://github.com/SaxenaAnushka102/NodeSmartHome/assets/58849657/beec6224-ad97-4dbe-b84b-9cad8e5c68e0)

#### 5. Select `locked mode` & click on `Enable` as rules are already set & third-party cannot read/write on our data. 

![image](https://github.com/SaxenaAnushka102/NodeSmartHome/assets/58849657/5343ce86-55b5-4753-a434-0c06ee2f0f08)

#### 6. 

6. Updation of Arduino Firebase Library Fingerprint

## Project Demo Video
https://user-images.githubusercontent.com/58849657/232340116-d4e9ff1b-995f-464c-add7-0dceb9ee5799.mp4

