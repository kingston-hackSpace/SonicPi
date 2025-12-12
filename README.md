# SonicPi

Sonic Pi is an open source programming environment originally designed to explore and teach programming concepts within schools through the process of creating new sounds.

Visit [sonic-pi.net](https://sonic-pi.net/)

----
# Test sound in yout Raspberry Pi

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

----
# Install SonicPi for RASPBERRY PI 

The following installation instructions are based on [SonicPi GitHub](https://github.com/sonic-pi-net/sonic-pi/blob/dev/BUILD-LINUX.md)

- Open the terminal, type:
  ```
  sudo apt update
  ```

- Install essential audio packages:

  ```
  sudo apt-get install -y build-essential git libssl-dev ruby-dev elixir erlang-dev erlang-xmerl supercollider-server sc3-plugins- server alsa-utils libasound2-dev cmake ninja-build pipewire-jack libspa-0.2-jack libwayland-dev libxkbcommon-dev libegl1-mesa-dev libx11-dev libxft-dev libxext-dev qpwgraph compton m4 libaubio-dev libpng-dev libboost-all-dev librtmidi-dev
  ```

- Install Qt5 packages:
  ```
  sudo apt install -y qtbase5-dev qttools5-dev qttools5-dev-tools libqt5svg5-dev libqt5opengl5-dev
  ```

- Check that Qt5 was installed properlly
  ```
  qmake --version
  ```

- This confirms the development tools are ready.

- Clone SonicPi source code from github:

  ```
  git clone https://github.com/sonic-pi-net/sonic-pi.git ~/Development/sonic-pi
  ```

- Go to the app directory:
  ```
  cd ~/Development/sonic-pi/app
  ```

- Run the build-all script for Linux. This step can take ome time (about 1hr):
  ```
  ./linux-build-all.sh
  ```

- Run SonicPi:
  ```
  cd ~/Development/sonic-pi/app/gui/qt
  ./sonic-pi
  ```

- Let's create a short-cut
  ```
  sudo ln -s ~/Development/sonic-pi/app/build/gui/sonic-pi /usr/local/bin/sonic-pi
  ```

- Now you can just open the Terminal and type:
  ```
  sonic-pi
  ```
  
  

  
