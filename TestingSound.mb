# Testing Sound output from RPi

**RPi model 5:** 

- NO JACK: The lastest RPi model 5 doesnt have a jack output as previous models.

- USB SPEAKER: Ideally, use a speaker with USB connection such as [this](https://thepihut.com/products/mini-external-usb-stereo-speaker). The RPi shoudl automatically recognize it and play sound with it.

- BLUETOOH:

  - Locate the Bluetooth icon at the top right of the screen and do left click > Add Device...
 
  - Select your speaker and Pair
 
  - Confirm Pairing as instructed
 
  - You should get the following message: "Pairing Successfull - ** right-click the volume icon to select as audio device**"
 
  - Right click on your Audio Icon (top right of the screen) and select your device
 
  - Test audio:
    ```
    aplay /usr/share/sounds/alsa/Front_Center.wav
    ```
  - Run Sonic Pi and Test audio using an example, or just "play 60"
 
  - If you don't get any audio, your need further configurations
 
  - Install pavucontrol:
    ```
    sudo apt install pavucontrol -y
    ```
  - 
    
 
  Note: Bluetooth connections are not advice for life performances as they can be unstable. 
