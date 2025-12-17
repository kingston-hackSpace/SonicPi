----
# Sonic Pi Audio Output

Set your audio output for Sonic Pi on a RPi

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
# CONFIGURATING qpwgraph
  
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

- Open the Terminal and create a folder named **qpwgraph** inside your .config directory:

`mkdir -p ~/.config/qpwgraph`

- If you closed Sonic Pi, open it again and link the audio nodes in the qpwgraph App, so you hear the sound coming from the speaker. 

- In the qpwgraph App, go to the menu

          Patchbay → Activated

          Patchbay → Save As…

- In the Save window:

  - Right click on the saving window and select ***Show hidden files***

  - More folders should now appear. Navigate to ***.config > qpwgraph***

- Name the file:

`sonicpi-headphones.qpwgraph`

- Save

- Close Sonic Pi and qpwgraph
  
----
# Automate qpwgraph + Sonic Pi at Launch

- Open the Terminal

- Create an autostart directory and file:

```
mkdir -p ~/.config/autostart
nano ~/.config/autostart/sonicpi-qpwgraph.desktop
```

- Copy/Paste the following content in it:

```
[Desktop Entry]
Type=Application
Name=Sonic Pi + Patchbay
Exec=qpwgraph --load /home/pi/.config/qpwgraph/sonicpi-headphones.qpwgraph & sonic-pi
X-GNOME-Autostart-enabled=true
```

- Save and Exit:
        Save: Ctrl + O → Enter
        Exit: Ctrl + X

- Reboot the RPi:

`sudo reboot`

- The following command (to type in the Terminal) will allow you to open Sonic Pi with a loaded qpwgrapgh route. 

`qpwgraph & sleep 1; sonic-pi`

- If you run any sounds in Sonic Pi now, it should automatically output through your speakers.
