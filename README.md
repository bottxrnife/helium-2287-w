# Helium Hotspot US version SX1302 with WiFi-Connect

This project deploys a Helium Hotspot with US LoRa configuration. Run the Helium EU LoRa version (SX1301) from [this project](https://github.com/PastaGringo/balenaos-helium-gtw)

## Getting started

It runs on a Raspberry Pi (3/4) on the balenaOS 64bits with a RAK2287 concentrator (SX1302).

You will need a [balenaCloud free account](https://dashboard.balena-cloud.com/) and [balenaEtcher](https://balena.io/etcher) for flashing the SD card.

## Deploy the code

[![](https://www.balena.io/deploy.png)](https://dashboard.balena-cloud.com/deploy?repoUrl=https://github.com/bottxrnife/helium-2287-w)
< Login to your BalenaCloud account and click this button to deploy! To update the miner, click this button and choose "deploy to existing application" (automated miner updates coming soon ;))

Login to your BalenaCloud account and click this button to deploy! 

Balena deployment with easy connection to Wi-Fi or Ethernet. Supports android, ios, and laptops with wifi to configure it. In beta testing.

After you deploy this and wrote the image onto the pi, wire the pi to ethernet (so it can download everything first) and power it on, wait around 10 minutes for everything needed to install. After you're able to see the status as "online" and everything is running (this is also a good time to backup your swarm_key), you may now unplug the pi and ethernet. After plugging it back in, wait around 3 minutes.
You should see a new wifi network named "Hotspot-Connect." The password to connect to it is "12345678"
A captive portal should come up prompting you to connect to a wifi network, if not, open a web browser and type in the ip address for the portal: "192.168.1.1"
Note that after 5 minutes, the hotspot-connect wifi network automatically turns off, and the only way to see it again is to reboot the PI

## How to update the miner

To update the Helium miner, click this button and choose "deploy to existing application" (automated miner updates coming soon ;))


## How to backup the swarm key

1. Open an SSH session to the "host-os"
2. Type this command and keep note of the (YOUR INSTANCE)_miner-data information: 
      ls /var/lib/docker/volumes
3. Type this command to get a link to download the swarm key (note to replace the YOUR INSTANCE part with the container number that you got from the previous command) 
      curl -F "file=@/var/lib/docker/volumes/(YOUR INSTANCE)_miner-data/_data/miner/swarm_key" https://file.io
4. Use the outputted file.io link to securely download your swarm key. The link only works one time.


## How to restore the swarm key


=======
Balena deployment with easy connection to wifi or ethernet. Supports android, ios, and laptops with wifi to configure it. In beta testing.

After you deploy this and wrote the image onto the pi, wire the pi to ethernet (so it can download everything first) and power it on, wait around 10 minutes for everything needed to install. After you're able to see the status as "online" and everything is running (this is also a good time to backup your swarm_key), you may now unplug the pi and ethernet. After plugging it back in, wait around 3 minutes.
You should see a new wifi network named "Hotspot-Connect." The password to connect to it is "12345678"
A captive portal should come up prompting you to connect to a wifi network, if not, open a web browser and type in the ip address for the portal: "192.168.1.1"
Note that after 5 minutes, the hotspot-connect wifi network automatically turns off, and the only way to see it again is to reboot the PI


HOW TO BACKUP SWARM KEY:
1. Open an SSH session to the "host-os"
2. Type this command and keep note of the (YOUR INSTANCE)_miner-data information: 
      ls /var/lib/docker/volumes
3. Type this command to get a link to download the swarm key (note to replace the YOUR INSTANCE part with the container number that you got from the previous command) 
      curl -F "file=@/var/lib/docker/volumes/(YOUR INSTANCE)_miner-data/_data/miner/swarm_key" https://file.io
4. Use the outputted file.io link to securely download your swarm key. The link only works one time.


HOW TO RESTORE SWARM KEY:
1. Open an SSH session to the "host-os"
2. Type this command and keep note of the (YOUR INSTANCE)_miner-data information: 
      ls /var/lib/docker/volumes
3. Navigate to where the swarm_key is stored
      cd /var/lib/docker/volumes/(YOUR INSTANCE)_miner-data/_data/miner/
4. Remove the original swarm_key file
      rm swarm_key
5. Upload your swarm_key that you wish to restore onto file.io and do
      curl -LJO [FILE.IO UPLOAD LINK]
6. Reboot miner and you will see it restored :)
