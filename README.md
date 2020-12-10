# helium-2287 US W

[![](https://www.balena.io/deploy.png)](https://dashboard.balena-cloud.com/deploy?repoUrl=https://github.com/bottxrnife/helium-2287-w)
< Login to your BalenaCloud account and click this button to deploy!


Balena deployment with easy connection to wifi. Supports android, ios, and laptops with wifi to configure it. In beta testing.

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
