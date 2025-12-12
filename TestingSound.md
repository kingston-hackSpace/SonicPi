# Testing Sound Output from Your Raspberry Pi

Follow the sound test instructions based on your Raspberry Pi model.

----
# RPi 4B - Hardware

----
# RPi 5 - Hardware

- NO HEADPHONE JACK: The lastest RPi model5 doesn't have a jack output like previous models.

- USB SPEAKER: Ideally, use a speaker with USB connection such as [this](https://thepihut.com/products/mini-external-usb-stereo-speaker). The Raspberry Pi should automatically recognise it and play sound through it.

- BLUETOOH SPEAKER:

  1. Click the Bluetooth icon at the top right of the screen and select Add Device…
 
  2. Select your speaker and choose Pair.
 
  3. Confirm Pairing as instructed on screen.
 
  4. You should see the message: "Pairing Successfull - ** right-click the volume icon to select as audio device**"
 
  5. Right-click the audio icon (top right) and select your Bluetooth device.
 
  6. Further configuration **PENDING**

*Note:* Bluetooth connections are not recommended for live performances, as they can be unstable.
 
----
# AUDIO TEST

  - Open your terminal and type:

    ```
    aplay /usr/share/sounds/alsa/Front_Center.wav
    ```

- The Raspberry Pi should play a sound that says "Front Center."
 

