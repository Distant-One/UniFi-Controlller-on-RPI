# UniFi-Controlller-on-RPI
How to: Installing the UniFi Controller on the Raspberry Pi
Following the instructions found at:
https://pimylifeup.com/rasberry-pi-unifi/
sudo apt update
sudo apt upgrade
sudo apt install rng-tools
sudo vi  /etc/default/rng-tools-debian
Within this file, find and uncomment the following line.
#HRNGDEVICE=/dev/hwrng
Replace With
HRNGDEVICE=/dev/hwrng
By uncommenting this line, we are adding to the amount of entropy (The amount of randomness) that the system has available.
The Raspberry Pi features an integrated random number generator that we can utilize to increase the entropy pool.
Once you have made the change, save the file by pressing <ESC> : wq
Finally, restart the rng-tools service by running the command below.
sudo systemctl restart rng-tools
Once the service has finished restarting, it should now be safe to proceed to the next section of this guide.
