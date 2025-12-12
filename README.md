# SonicPi

Sonic Pi is an open source programming environment originally designed to explore and teach programming concepts within schools through the process of creating new sounds.

It is also widely used by hobbyists, musicians, and educators for live coding performances, music composition, sound experimentation, and learning programming in a fun, interactive way.

Visit [sonic-pi.net](https://sonic-pi.net/)

----
# Test sound in yout Raspberry Pi

Before diving into audio programming, let's ensure your Raspberry Pi is outputting sound correctly. Please [follow this instructions](https://github.com/kingston-hackSpace/SonicPi/blob/main/TestingSound.md)

----
# Install SonicPi for RASPBERRY PI 

- Run your Raspberry Pi, which should be also connected to the internet. 

- Download the SonicPi 64bi-package using [this link](https://sonic-pi.net/files/releases/v4.6.0/sonic-pi_4.6.0_2_trixie.arm64.deb). Last update: Dec 2025.

- Open the yelow folder located at the top left of the screen, locate *Downloads*

- In your Downloads, you should see a .zip file titled "sonic-pi_4.6.0_2_trixie.arm64.deb"

- Right-click on it and select *Package Install*. Confirm the installation. You will be asked for the RPi's password, type *pi* (password if you followed previous hackSpace's RPi installation settings)

- Let the software to start.

----
# HDMI output

- By default the Sonic-Pi sound output will be connected to HDMI and can be heard in the speakers in your monitor.
  
----
# CHANGING THE AUDIO OUTPUT PATH. 

Unlike for other applications, right clicking the volume control on the Raspberry Pi menu bar will not change the audio destination for Sonic Pi. Instead, you can use a program **qpwgraph** which the installer adds to the Audio Section of the Application Menu. Read more about it [here](https://sonic-pi.net/files/releases/v4.5.0/README-Sonic-Pi-Raspberry-Pi-OS.txt)


----
# Configurating qpwgraph 

- Plug your speaker to the Raspberry Pi Model4B jack output.
  
- Run your Sonic-Pi App. Sonic-Pi needs to be running to configure the route from qpwgraph to the speakers.

- Select the Raspberry Pi icon at the top-left of your Desktop

- Select *Sound & Video*

- Select *qpwgraph*

- A new software should open. This is qpwgraph.

- Link ***SuperCollider*** to ***Build-in Audio Stereo***

- Without closing *qpwgraph*, go back to SonicPi and play any sounds. Your speaker should be reproducing the sounds now. 
 
- If you need further help, please watch [this video tutorial](https://www.youtube.com/watch?v=d5MhUZHZ1uw)

----
# Saving a qpwgraph to speaker route

- Create a folder called qpwgraph, located at .config

- one you have linked the Super coliider block to your speakers, go to Patchbay > SAve As...

- name your file sonicpi-headphones.qpwgraph

- save the file in the .config/qpwgraph folder your just created
  
----
# Automate qpwgraph + SonicPi at launch

- Create an autostart file:

  ```
  mkdir -p ~/.config/autostart
  nano ~/.config/autostart/sonicpi-qpwgraph.desktop
  ```

- Tyope the following in it:
```
[Desktop Entry]
Type=Application
Name=Sonic Pi + Patchbay
Exec=qpwgraph --load /home/pi/.config/qpwgraph/sonicpi-headphones.qpwgraph & sonic-pi
X-GNOME-Autostart-enabled=true
```

- save and exit

- reboot the pi

- on terminal, type: `qpwgraph & sleep 1; sonic-pi
  
