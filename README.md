# SonicPi

**Sonic Pi** is an open source programming environment designed to explore programming through creating sounds. It is widely used by hobbyists, musicians, and educators for live coding performances, music composition and sound experimentation.

Visit [sonic-pi.net](https://sonic-pi.net/)

----
# First steps:

- Turn on your Raspberry Pi and make sure it’s connected to the internet.

- Open the terminal and type:

        sudo apt update

- Install PulseAudio utility tools:

        sudo apt install pulseaudio-utils -y

- Test audio:

        paplay /usr/share/sounds/alsa/Front_Center.wav

- The Raspberry Pi should play a sound that says "Front Center."


----
# Installing Sonic Pi on RASPBERRY PI 

- Open this tutorial directly in your RPi's browser

- Download the SonicPi 64-bitpackage using [this link](https://sonic-pi.net/files/releases/v4.6.0/sonic-pi_4.6.0_2_trixie.arm64.deb). The installation package should download automatically.

- Open the File Manager (yellow folder icon at the top-left of the desktop)

- Locate the *Downloads* folder

- In your Downloads, you should see a .zip file titled "sonic-pi_4.6.0_2_trixie.arm64.deb"

- Right-click on it and select *Package Install*. Confirm the installation. You will be asked for the RPi's password, type *pi* ("pi" should be your password if you followed previous hackSpace's instructions)

- Wait for the installation to complete.

- Open Sonic Pi using the Terminal by typing:

          sonic-pi
  
- Test Sonic Pi.

- If you don't get any audio, follow the instructions below. 


----
# HDMI output

- By default, Sonic Pi outputs audio through HDMI. If your monitor has built-in speakers, you will hear the sound there.

- If you want to use external speakers via the Raspberry Pi’s 3.5 mm jack, additional setup is required.
  
----
# CHANGING THE AUDIO OUTPUT PATH

- Sonic Pi relies on [SuperCollider](https://supercollider.github.io/) to generate audio. On recent Raspberry Pi OS versions, SuperCollider may not automatically find a playable output. To route audio to your speakers, you need to configure the output manually using **qpwgraph**. Read more [here](https://sonic-pi.net/files/releases/v4.5.0/README-Sonic-Pi-Raspberry-Pi-OS.txt)


**Why qpwgraph is required:**

- Sonic Pi relies on SuperCollider to generate audio.

- PipeWire only creates SuperCollider audio nodes when qpwgraph is running.

- Without qpwgraph open, Sonic Pi produces no sound — even if the patch is saved or routing rules exist.


----
# CONFIGURATING QPWGRAPGH 
  
- Make sure Sonic Pi is running, as SuperCollider must be active for qpwgraph to detect its audio nodes.

- Clicl the Raspberry Pi icon at the top-left of your Desktop.

- Select *Sound & Video* > *qpwgraph*

- A new window will open displaying audio nodes. This is qpwgraph.

- Link the ***SuperCollider*** node to ***Build-in Audio Stereo***. Watch [this video for further help](https://www.youtube.com/watch?v=d5MhUZHZ1uw)

- Without closing *qpwgraph*, go back to Sonic Pi and play any sounds.

- You should now hear the audio through your speakers.


**IMPORTANT NOTE!!**

You will need to link SuperCollider to your speakers *every time* you use Sonic Pi.

To avoid doing this manually each time, you can *automate* the process. Follow the steps below to set this up.

----
# Saving a qpwgraph route

- Go back to the Terminal and create a folder named qpwgraph inside your .config directory:

          mkdir -p ~/.config/qpwgraph

- If you closed Sonic Pi, open it again and link the audio nodes in the qpwgraph App, so you hear the sounds. 

- In the qpwgraph App, go to the menu

          Patchbay → Save As…

- Before saving, we need to locate out saving folder as follows:

          - Right click on the saving window > Show hidden files

          - More folders should had appeared. Navigate to your now visible *.config > qpwgraph*

- Name the file:

          sonicpi-headphones.qpwgraph

- Save

- Close Sonic Pi and qpwgraph
  
----
# Automate qpwgraph + SonicPi at launch

- Open the Terminal

- Create an autostart file:

        mkdir -p ~/.config/autostart
        nano ~/.config/autostart/sonicpi-qpwgraph.desktop

- Type the following in it:

        [Desktop Entry]
        Type=Application
        Name=Sonic Pi + Patchbay
        Exec=qpwgraph --load /home/pi/.config/qpwgraph/sonicpi-headphones.qpwgraph & sonic-pi
        X-GNOME-Autostart-enabled=true

- save and exit

- reboot the pi

- on terminal, type: `qpwgraph & sleep 1; sonic-pi
  
