# neomesh-LoRa-Tracker

## What is it
An Arduino-based bike tracker that transmits its position through the LoRaWAN network.

## Components
- 1x TTGO T-Beam V2
- 1x TTGO T-Beam case

## Method
Use the onboard GPS antenna of the TTGO to get the GPS location and send that location to the neomesh LoRaWAN server, which is running on The Things Network (TTN).

## Code
The code sequence is written in C++, but based on Arduino. It therefore uses Arduino libraries and needs an Arduino IDE installation. This version is written on VSCode and uses PlatformIO to manage it.

### Dependencies
Libraries: LMIC, HAL and SPI.

### Code specifics
First of all, the code is based on [this](https://github.com/rjmendez/ttgo-tbeam-ttn-tracker) GitHub repository.
Basically, you input the APPEUI, DEVEUI and APPKEY (that you can find on the neomesh TTN application) as described in the code, and then select the correct LMIC pins for the TTGO board (nss = 18, rst = 23, dio = {26, 33, 32}). With that setup done, the board should find be able to connect to the TTN application, find a GPS fix and send the data payload.
An excellent resource for this project is [AEQ-Web](https://www.aeq-web.com/ttgo-lilygo-esp32-gps-tracker-lorawan-setup/?lang=en).

## Current status
The project hasn’t been finished due to a specific problem: The board doesn’t connect to the TTN application. It seems not to recieve the LoRaWAN signal, or, if it is recieving it, it can’t access the application. They keys have been checked.

## Next steps
Some work has to be done:
- With the update to TTN, a new application could be setup, allowing new keys to be tried out.
- Revising the code in search of missed or wrong PIN definitions.

## Appendix
- [TTGO T-Beam Pinout](images/boardPinout.png)
