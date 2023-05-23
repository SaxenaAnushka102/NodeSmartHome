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

![image](https://github.com/SaxenaAnushka102/NodeSmartHome/assets/58849657/8c96b6b8-85a1-416a-8452-fa6e14934238)

#### 2. Click on `Software` tab.

![image](https://github.com/SaxenaAnushka102/NodeSmartHome/assets/58849657/e1740690-89dd-4d8f-b52c-f094e851cad7)

![image](https://github.com/SaxenaAnushka102/NodeSmartHome/assets/58849657/969acddd-197d-44df-9501-064e29593213)

#### 3. Scroll down to Downloads.

![image](https://github.com/SaxenaAnushka102/NodeSmartHome/assets/58849657/d5b98d2c-d3b7-43e2-827a-ec7a7646045f)

![image](https://github.com/SaxenaAnushka102/NodeSmartHome/assets/58849657/2898eff9-ba1e-4f28-9faa-62857ca9e299)

#### 4. Download the .exe file according to your Operatng System. I have got "Windows 10 and newer, 64 bits" for my system.

![image](https://github.com/SaxenaAnushka102/NodeSmartHome/assets/58849657/3a84b0ed-baab-40a7-a135-ac604c8edbe9)

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

#### 6. In the Realtime Database you just created, go to `Rules` > `Edit rules` to set the read and write permissions to true. Click `Publish` once you're done.

![image](https://github.com/SaxenaAnushka102/NodeSmartHome/assets/58849657/09134f6a-b8de-4825-a0c8-4bf56ef015b0)

#### 7. Go to `Data` tab & copy the Reference URL from top panel. Save this in Notepad.

![image](https://github.com/SaxenaAnushka102/NodeSmartHome/assets/58849657/87e6686f-635e-414b-9209-014c05e1d37d)

#### 8. Open the file `4relay_mit.ino` & paste the link copied in the last step (w/o https) in the third line as shown.

![image](https://github.com/SaxenaAnushka102/NodeSmartHome/assets/58849657/97479d09-4db1-439f-81d5-3d8695631d53)

#### 9. Go to the Firebase Project & head on to the `Settings` > `Project Settings` > `Service accounts` > `Database secrets`. Copy the secret key.

![image](https://github.com/SaxenaAnushka102/NodeSmartHome/assets/58849657/8852dddc-26b3-4be6-b732-b74599557a07)

![image](https://github.com/SaxenaAnushka102/NodeSmartHome/assets/58849657/2a30f03b-b138-45fe-b35d-9352722bac88)

#### 10. Go to Arduino IDE & paste the secret key into line 4 of `4relay_mit.ino` as shown.

![image](https://github.com/SaxenaAnushka102/NodeSmartHome/assets/58849657/b0e42391-53a9-4238-9011-bbe9370bae60)

#### 11. Write the name of your WiFi & password in the third & fourth line of `4relay_mit.ino`.

#### 12. Connect LEDs on indicated pins (ex.- D1, D2, D5, D6) or connect relay input to the pins.

#### 13. Go to https://appinventor.mit.edu/

![image](https://github.com/SaxenaAnushka102/NodeSmartHome/assets/58849657/62686d6a-da07-4a35-b1be-f40f611d5f93)

#### 14.  Click on `Create Apps` and Login with your mail. Go to `Projects` > `Import Project (.aia) from my computer` and upload `smart home app.aia`

![image](https://github.com/SaxenaAnushka102/NodeSmartHome/assets/58849657/a5fda0b9-99af-4d4d-954b-b58d20353bad)

#### 15. After the App is loaded, click on `FirebaseDB1` and on right panel, paste your secret key in `Firebase Token` field and Reference URL in `Firebase URL` fields. Set bucket value to NULL.

![image](https://github.com/SaxenaAnushka102/NodeSmartHome/assets/58849657/004df2c6-e982-4aa9-8cb2-bf46bfe26b1d)

#### 16. Click on `Connect` > `AI Companion` 

![image](https://github.com/SaxenaAnushka102/NodeSmartHome/assets/58849657/81ba685c-1bd6-40cc-823c-e10e339695ba)

#### 17. Open the MIT AI Copanion App in your Smart Phone. You'll see a Smart Home App once the QR is scanned successfully. 

![image](https://github.com/SaxenaAnushka102/NodeSmartHome/assets/58849657/8a31b660-f049-4b8e-9f02-9c63dad6837c)

![image](https://github.com/SaxenaAnushka102/NodeSmartHome/assets/58849657/c3c00cc9-208e-4e40-9815-3e55e75086ad)


* ##  Updation of Arduino Firebase Library Fingerprint

#### 1. Go to the path where the FirebaseArduino Library is installed. Now go to `firebase-arduino-master` < `src` & open FirebaseHttpClient.h in Notepad.

![image](https://github.com/SaxenaAnushka102/NodeSmartHome/assets/58849657/cad45bde-7f33-40f6-8b3b-8a777d9dda44)

![image](https://github.com/SaxenaAnushka102/NodeSmartHome/assets/58849657/81574663-ed11-4570-ba16-1fa5e64d98f3)

#### 2. Now, we will change Firebase Fingerprint

![image](https://github.com/SaxenaAnushka102/NodeSmartHome/assets/58849657/e2cc057a-755b-4b4f-b99f-643c5421a150)

#### 3. Go to https://www.grc.com/fingerprints.htm & scroll down to paste the Firebase URL & click on `Fingerprint Site`.

![image](https://github.com/SaxenaAnushka102/NodeSmartHome/assets/58849657/9801484a-7261-4d9b-b8da-fa247c8e62b3)

#### 4. Copy the generated Key & replace in the notepad as shown & Save the changes. Close the Arduino IDE.

![image](https://github.com/SaxenaAnushka102/NodeSmartHome/assets/58849657/6cacf3b1-80ae-47af-a256-60cad23720d7)

![image](https://github.com/SaxenaAnushka102/NodeSmartHome/assets/58849657/94fae54e-e7f9-40c2-a27f-43e2cd0b562b)

#### 5. TA-DAAAA! The SSL security is now configured & start connecting the Board to see the project working!!!



## Project Demo Video
https://user-images.githubusercontent.com/58849657/232340116-d4e9ff1b-995f-464c-add7-0dceb9ee5799.mp4

