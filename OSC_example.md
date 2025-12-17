### Client.py

```
from pythonosc import osc_message_builder
from pythonosc import udp_client
import time
import random

sender = udep_client.SimpleUDPClient('127.0.0.1', 4560)

while True:
    note = random.randint(48, 72)
    sender.send_message('/trigger/prophet', [note])
    time.sleep(1)
```
----
### Server_SonicPi.txt
```
live_loop :foo do

    use_real_time #sync with OSC incoming messages

    #a is the note that the synth will play, which we can fix or make a variable to receive OSC msg
    #a = 60 #fixed value
    #a = rand(48..72)
    a = sync "/osc*/trigger/prophet"

    b = 80
    c = 1.5

    synth :prophet, note:a, cutoff:b, sustain:c

    sleep c
end
```
