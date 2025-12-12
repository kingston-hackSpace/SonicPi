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

- Open your RPi browser (top left icon) and open [this link](https://sonic-pi.net/#rp). It might take some seconds to 

- Download the option "64 bit package" from [this link]


-------------

- By default the Sonic-Pi sound output will be connected to HDMI and can be heard in the speakers
in your monitor.

- CHANGING THE AUDIO OUTPUT PATH. Unlike for other applications,right clicking the volume control on the Raspberry Pi menu bar will not change the audio destination for Sonic Pi. Instead, you can use a program qpwgraph which the installer adds to the Audio Section of the Application Menu. Read more about it [here](https://sonic-pi.net/files/releases/v4.5.0/README-Sonic-Pi-Raspberry-Pi-OS.txt)

- Further help? See [this video tutorial](https://www.youtube.com/watch?v=d5MhUZHZ1uw)

- or:

- route:

mkdir -p ~/.config/pipewire/media-session.d
nano ~/.config/pipewire/media-session.d/default-connections.conf


context.modules = [
   {
        name = libpipewire-module-loopback
        args = {
            node.name = "supercollider-output"
            node.description = "SuperCollider to Headphone Jack"
            target = "alsa_output.hw_2_0"
        }
    }
]


  

  
