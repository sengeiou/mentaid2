# wearable_nRF52_iOS
This is an iOS Swift application for communicating with an nRF52-based wearable. The application assumes you are using your own custom BLE service. In general, you will have to modify some of the code related to the BLE services to get it to work with your particular wearable. The firmware (https://github.com/jliphard/wearable_nRF52_Firmware) for our Stanford University-funded wearable is also public, so you can use that as a starting point for your own research or other use.  

The code started out as a simple modification of Nordic's excellent nRF toolbox (https://github.com/NordicSemiconductor/IOS-nRF-Toolbox). 

The major differences are that (1) the data are now contained within a separate datamodel, (2) that the app uses a standard tab bar controller to allow the user to navigate among different views, and (3) that we use one DataModel.sharedInstance along with NotificationCenter.default.post() to get the various charts and data outlets across all the views supplied with fresh data from the device.

It should be straightforward to reuse/modify this code for many different wearables. In case you are curious, our hardware contains several sensors, a Nordic nRF52 MCU, and some SPI NOR-FLASH for data logging. The major next step will be add data uploading to pubnub and to encrypt the bluetooth. 

The code is under very active development, so expect things to change rapidly without notice. 
