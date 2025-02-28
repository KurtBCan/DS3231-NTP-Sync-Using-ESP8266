# ESP8266 NTP Synchronization for the DS3231 RTC

By: Kurt Cantrell

Description: Code to synchronize the DS3231 RTC breakout board using the Adafruit HUZZAH ESP8266 as an NTP network client. This allows for manual, instantaneous NTP synchronization of the DS3231 breakout board. Required libraries include RTClib, NTPClient, and the ESP8266 board library. This code was created by using and combining example code fragments from the RTClib and NTPClient libraries' examples. Time delays in the breakout boards or due to processing time is not accounted for (deemed negligible).

Why this was needed: The current time reset in the RTClib library for the DS3231 breakout board sets the time of the RTC to the time **WHEN THE CODE FOR THE MICROCONTROLLER COMPILED**. This was creating time offsets of **> 20 seconds** between the RTC and the time shown on a computer/phone. This code was **VISUALLY VERIFIED BY COMPARING RTC SERIAL TIMESTAMP PRINTS TO A RUNNING CLOCK OPENED ON AN INTERNET BROWSER** (no error calculations were created).

I've included an image demonstrating I2C setup for connection between ESP8266 and DS3231 breakout boards. SDA and SCL of the DS3231 go to pins #4(SDA) and #5(SCL) of the ESP8266. Vin to 3V pin and GND to GND.

![RTC_Sync_Using_ESP8266](https://github.com/user-attachments/assets/cc5b917b-4d12-4002-9a2a-231c42d7aaae)
