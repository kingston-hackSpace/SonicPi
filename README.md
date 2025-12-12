# SonicPi

Sonic Pi is an open source programming environment originally designed to explore and teach programming concepts within schools through the process of creating new sounds.

It is also widely used by hobbyists, musicians, and educators for live coding performances, music composition, sound experimentation, and learning programming in a fun, interactive way.

Visit [sonic-pi.net](https://sonic-pi.net/)

----
# Test sound in yout Raspberry Pi

Before diving into audio programming, let's ensure your Raspberry Pi is outputting sound correctly. Please [follow this instructions](https://github.com/kingston-hackSpace/SonicPi/blob/main/TestingSound.md)

----
# Install SonicPi for RASPBERRY PI 

The following installation instructions are based on [this guide to install SonicPi on a RPi](https://github.com/sonic-pi-net/sonic-pi/blob/dev/BUILD-RASPBERRY-PI.md) and assume a **Debian 64-bit** configuration.

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
  
  

  
