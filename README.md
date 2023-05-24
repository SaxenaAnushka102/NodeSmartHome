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

![image](https://github.com/SaxenaAnushka102/NodeSmartHome/assets/58849657/e4dc0101-0da3-4fb0-a9c5-f498529c6ba4)

#### 2. Click on `Software` tab.

![image](https://github.com/SaxenaAnushka102/NodeSmartHome/assets/58849657/e1740690-89dd-4d8f-b52c-f094e851cad7)

#### 3. Scroll down to Downloads.

![image](https://github.com/SaxenaAnushka102/NodeSmartHome/assets/58849657/d5b98d2c-d3b7-43e2-827a-ec7a7646045f)

#### 4. Download the .exe file according to your Operatng System. I have got "Windows 10 and newer, 64 bits" for my system.

![image](https://github.com/SaxenaAnushka102/NodeSmartHome/assets/58849657/3a84b0ed-baab-40a7-a135-ac604c8edbe9)

* ### ESP8266 add-on in Arduino IDE
#### 1. Go to the Arduino IDE and on the tabs listed on the top ribbon, click on `File` > `Preferences`.

![image](https://github.com/SaxenaAnushka102/NodeSmartHome/assets/58849657/7470bd67-19dc-40bd-9fdc-07908a1c6b49)

#### 2. Enter https://arduino.esp8266.com/stable/package_esp8266com_index.json into the "Additional boards Manager URLs" field as shown below & click OK.

![image](https://github.com/SaxenaAnushka102/NodeSmartHome/assets/58849657/681cceb2-b31c-4eec-b5c3-5ca8102d1979)

#### 3. Go to `Tools` > `Boards` > `Boards Manager...`

![image](https://github.com/SaxenaAnushka102/NodeSmartHome/assets/58849657/1a80d242-b549-4a30-863a-9f4eb4bc5a02)

#### 4. Search for ESP8266 and install version 2.7.3

![image](https://github.com/SaxenaAnushka102/NodeSmartHome/assets/58849657/74ce3e0f-ce9c-4689-b55f-9f6372ec5392)


* ## Installation of Firebase Library 

#### 1. Go to https://github.com/FirebaseExtended/firebase-arduino

![image](https://github.com/SaxenaAnushka102/NodeSmartHome/assets/58849657/e0a40e0c-ff2b-4b19-a026-e9b860f9478c)

#### 2. In the Repository, click on `Code` then click on `Download ZIP`

![image](https://github.com/SaxenaAnushka102/NodeSmartHome/assets/58849657/152483ff-ac58-4bc3-a40d-e49978f384e9)

#### 3. In Arduino IDE click on the `Sketch` tab listed on the top ribbon, click on `Include Library` > `Add .ZIP Library...`

![image](https://github.com/SaxenaAnushka102/NodeSmartHome/assets/58849657/1f7af268-9508-4c9d-87ae-1f678b6f10ba)

#### 4. Go to the ZIP folder you just downloaded, Select & click Open

![image](https://github.com/SaxenaAnushka102/NodeSmartHome/assets/58849657/e8443d4e-cfb8-427a-ab0e-1824c7d6f772)

FirebaseArduino now depends on ArduinoJson library


* ## Installation of Arduino Json Library(version-5.13.2)

#### 1. In Arduino IDE click on the Sketch tab listed on the top ribbon, click on `Include Library` > `Manage Library`

![image](https://github.com/SaxenaAnushka102/NodeSmartHome/assets/58849657/3dff617a-64b2-4260-b420-f9f14ccc1234)

#### 2. Search for ArduinoJson by Benoit and install version 5.13.2

![image](https://github.com/SaxenaAnushka102/NodeSmartHome/assets/58849657/775d5422-dca9-4aec-bf3b-872b7609d10a)


* ## Firebase Account Creation and setting up the project

#### 1. Go to https://firebase.google.com/

![image](https://github.com/SaxenaAnushka102/NodeSmartHome/assets/58849657/a327faed-94d9-4124-b992-a325a215dc91)

#### 3. Choose Default Account on Firbase & click on `Create Project`.

![image](https://github.com/SaxenaAnushka102/NodeSmartHome/assets/58849657/6266a25c-17cd-4f85-940e-56890d742e4b)

![image](https://github.com/SaxenaAnushka102/NodeSmartHome/assets/58849657/3ed86595-6f68-449d-9c12-0bf37c638f93)

#### 4. From the left nav bar, go to `Build` > `Realtime Database` > `Create Database`

![image](https://github.com/SaxenaAnushka102/NodeSmartHome/assets/58849657/33b5956d-563c-44c8-9090-4d47a0ba5086)

#### 5. Select `locked mode` & click on `Enable` as rules are already set & third-party cannot read/write on our data. 

![image](https://github.com/SaxenaAnushka102/NodeSmartHome/assets/58849657/df1f8e0e-174c-470e-a0b8-9f0f437abf60)

#### 6. In the Realtime Database you just created, go to `Rules` > `Edit rules` to set the read and write permissions to true. Click `Publish` once you're done.

![image](https://github.com/SaxenaAnushka102/NodeSmartHome/assets/58849657/a7a11790-02ad-446b-9975-40f59a5ae358)

#### 7. Go to `Data` tab & copy the Reference URL from top panel. Save this in Notepad.

![image](https://github.com/SaxenaAnushka102/NodeSmartHome/assets/58849657/89a086ad-9f38-4bc5-9615-859ab6c77456)

#### 8. Open the file `4relay_mit.ino` & paste the link copied in the last step (w/o https) in the third line as shown.

![image](https://github.com/SaxenaAnushka102/NodeSmartHome/assets/58849657/32a6552d-3b6c-4529-8299-12bbb633731f)

#### 9. Go to the Firebase Project & head on to the `Settings` > `Project Settings` > `Service accounts` > `Database secrets`. Copy the secret key.


![image](https://github.com/SaxenaAnushka102/NodeSmartHome/assets/58849657/529818a6-9fda-4f18-8d8f-a203167678c1)

![image](https://github.com/SaxenaAnushka102/NodeSmartHome/assets/58849657/9f0e58a8-7ee9-49eb-ac29-27a502bb55d9)

#### 10. Go to Arduino IDE & paste the secret key into line 4 of `4relay_mit.ino` as shown.

![image](https://github.com/SaxenaAnushka102/NodeSmartHome/assets/58849657/51421c52-e9d4-4155-aaa8-eb6f73174749)

#### 11. Write the name of your WiFi & password in the third & fourth line of `4relay_mit.ino`.

#### 12. Connect LEDs on indicated pins (ex.- D1, D2, D5, D6) or connect relay input to the pins.

#### 13. Go to https://appinventor.mit.edu/

![image](https://github.com/SaxenaAnushka102/NodeSmartHome/assets/58849657/0a6f722d-3bb1-46a7-aa8f-23a9b967d541)

![image](https://github.com/SaxenaAnushka102/NodeSmartHome/assets/58849657/de997cc9-5666-4439-82a3-d06a3cf350c6)

#### 14.  Click on `Create Apps` and Login with your mail. Go to `Projects` > `Import Project (.aia) from my computer` and upload `smart home app.aia`

![image](https://github.com/SaxenaAnushka102/NodeSmartHome/assets/58849657/9b1c85a4-c097-49e8-a72c-2ee0616f1570)

#### 15. After the App is loaded, click on `FirebaseDB1` and on right panel, paste your secret key in `Firebase Token` field and Reference URL in `Firebase URL` fields. Set bucket value to NULL.

![image](https://github.com/SaxenaAnushka102/NodeSmartHome/assets/58849657/c3b66616-aff1-4ddd-a058-4b5b735d006a)

#### 16. Click on `Connect` > `AI Companion` 

![image](https://github.com/SaxenaAnushka102/NodeSmartHome/assets/58849657/107c2a3b-b896-4388-a905-a3856f84138a)

#### 17. Open the MIT AI Copanion App in your Smart Phone. You'll see a Smart Home App once the QR is scanned successfully. 

![image](https://github.com/SaxenaAnushka102/NodeSmartHome/assets/58849657/fd4e0054-5304-439d-999b-d965df6e6645)

![image](https://github.com/SaxenaAnushka102/NodeSmartHome/assets/58849657/932136a9-37ba-4310-b83d-85c7ff0f5590)


* ##  Updation of Arduino Firebase Library Fingerprint

#### 1. Go to the path where the FirebaseArduino Library is installed. Now go to `firebase-arduino-master` > `src` & open FirebaseHttpClient.h in Notepad.

![image](https://github.com/SaxenaAnushka102/NodeSmartHome/assets/58849657/3f518d99-2e3f-4919-847d-dbe3022d87fe)

![image](https://github.com/SaxenaAnushka102/NodeSmartHome/assets/58849657/68a9c360-e761-475a-be9c-237fafaa5e44)

#### 2. Now, we will change Firebase Fingerprint

![image](https://github.com/SaxenaAnushka102/NodeSmartHome/assets/58849657/3b14c607-6162-4d87-ab7d-87deaf427078)

#### 3. Go to https://www.grc.com/fingerprints.htm & scroll down to paste the Firebase URL & click on `Fingerprint Site`.

![image](https://github.com/SaxenaAnushka102/NodeSmartHome/assets/58849657/112d9f57-fb8d-4aa8-85fa-2e07389f63f3)

![image](https://github.com/SaxenaAnushka102/NodeSmartHome/assets/58849657/9801484a-7261-4d9b-b8da-fa247c8e62b3)

#### 4. Copy the generated Key & replace in the notepad as shown & Save the changes. Close the Arduino IDE.

![image](https://github.com/SaxenaAnushka102/NodeSmartHome/assets/58849657/cfad931c-b4c5-4742-b7de-11ee64be47b4)

![image](https://github.com/SaxenaAnushka102/NodeSmartHome/assets/58849657/21c40a2d-4b0c-418e-8e26-a7b16c709ce0)

#### 5. TA-DAAAA! The SSL security is now configured & start connecting the Board to see the project working!!!



## Project Demo Video
https://user-images.githubusercontent.com/58849657/232340116-d4e9ff1b-995f-464c-add7-0dceb9ee5799.mp4

