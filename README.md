# ESP32-42e-Paper-Weather-Display-

This fork is based on David Bird's excellent e-Paper weather display.  I have added code to receive Temperature & Humidity readings from up to 3x F007TH Thermometer / Hygrometers.  The 433MHz Receive & Decode is based on the work by:
 
 Rob Ward (whose Manchester Encoding reading by delay rather than interrupt
 is the basis of this code)
 https://github.com/robwlakes/ArduinoWeatherOS
 
 The work of 3zero8 capturing and analysing the F007th data
 http://forum.arduino.cc/index.php?topic=214436.0
 
 The work of Volgy capturing and analysing the F007th data
 https://github.com/volgy/gr-ambient
 
 Marco Schwartz for showing how to send sensor data to websites
 http://www.openhomeautomation.net/

Additional Features:
* 433MHz Temperature / Humidity receive.  Channels 1, 2 & 3 (Set by DIP switches on Tx) are displayed.
  These are labeled: Indoor (Ch 1), Outdoor (Ch 2) and Workshop (Ch 3)
  If no signal is received on Ch2, the Temp & Humidity from Open Weather is displayed in it's place.
  
* SSID1 & SSID2 are implemented in owncredentials2.h to point to a main and backup WiFi source.  I've also added CITY1 & CITY2 
  in the same way.  CITY1 is used if the unit establishes a connection to SSID1 and CITY2 for SSID2.  This was so I could 
  use the same unit at home and work and it would read correctly.


A weather display for the 4.2" WaveShare display

OPEN WEATHER MAP VERSION

Go to Sketch > Include Library... > Manage Libraries.... Then, for each library, put its name into the text field to have its metadata pulled from the internet and displayed below. Select the latest version and install it. Make sure to come back to this dialog from time to time to keep each library up to date. Also make sure that you only have one version of each of the libraries installed.

'Mini Grafx' by Daniel Eichhorn 'ESP8266 WeatherStation' by Daniel Eichhorn (required for additional fonts) Download the software and install all 3 files in the same sketch folder.

ESP32_OWM_Current_Forecast_29_epaper_vX always choose the latest version ESP32_OWM_Current_Forecast_42_epaper_vX always choose the latest version ESP32_OWM_Current_Forecast_75_epaper_vX always choose the latest version

owm_credentials2.h

ArialRounded.h

Obtain your OWM API key - it's free

Edit the owm_credentials2.h file in the IDE (TAB at top of IDE) and change your Language, Country, choose your units Metric or Imperial and be sure to find a valid weather station location on OpenWeatherMap, if your display has all blank values your location does not exist!.
OPEN WEATHER MAP VERSION - STREAMING JSON

This version requires *** Arduino JSON v6 or above *** it streams the Openweather and processes the data as received, rather than downloading all the data first, then decoding it. It uses a lot less memory this way.

Go to Sketch > Include Library... > Manage Libraries.... Then, for each library, put its name into the text field to have its metadata

Compile and upload the code - Enjoy!
