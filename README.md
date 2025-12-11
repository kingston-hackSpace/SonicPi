# SonicPi

Sonic Pi is an open source programming environment originally designed to explore and teach programming concepts within schools through the process of creating new sounds.

Visit [sonic-pi.net](https://sonic-pi.net/)



----
# Install SonicPi for RASPBERRY PI 

The following installation instructions are based on [SonicPi GitHub](https://github.com/sonic-pi-net/sonic-pi/blob/dev/BUILD-LINUX.md)

- Open the terminal, type:
  ```
  sudo apt update
  ```

- Install essential audio packages:
  ```
sudo apt-get install -y build-essential git libssl-dev ruby-dev elixir erlang-dev erlang-xmerl supercollider-server sc3-plugins-server alsa-utils libasound2-dev cmake ninja-build pipewire-jack libspa-0.2-jack libwayland-dev libxkbcommon-dev libegl1-mesa-dev libx11-dev libxft-dev libxext-dev qpwgraph compton m4 libaubio-dev libpng-dev libboost-all-dev librtmidi-dev
  ```

- Install Qt5 packages:
  ```
  sudo apt install -y qtbase5-dev qttools5-dev qttools5-dev-tools libqt5svg5-dev libqt5opengl5-dev
  ```

- Check that Qt5 was installed properlly
  ```
  qmake --version
  ```

- Expected output should show Qt version 3.x. This confirms the development tools are ready.

- Clone SonicPi source code from github:

  ```
  git clone https://github.com/sonic-pi-net/sonic-pi.git ~/Development/sonic-pi
  ```
