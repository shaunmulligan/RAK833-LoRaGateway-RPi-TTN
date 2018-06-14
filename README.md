# The Things Network: RAK833-based gateway

Reference setup for [The Things Network](http://thethingsnetwork.org/) gateways based on the RAK833 USB concentrator with a Raspberry Pi host.

This installer targets the **USB interface** of the board.


## Setup based on Raspbian image

- Download [Raspbian Stretch with Desktop](https://www.raspberrypi.org/downloads/raspbian/)
- Follow the [installation instruction](https://www.raspberrypi.org/documentation/installation/installing-images/README.md) to create the SD card
- Start your RPi connected to Ethernet (Wi-Fi or Wire)
- Install RAK833 on mPCIE2USB board and plug it to RPi
  
- Configure locales and time zone

- Make sure you have an updated installation and install `git` (open Raspbian's Terminal):

        $ sudo apt-get update
        $ sudo apt-get upgrade
        $ sudo apt-get install git
 
- Clone [the installer](https://github.com/RAKWireless/RAK833-LoRaGateway/) and start the installation

        $ git clone https://github.com/RAKWireless/RAK833-LoRaGateway.git ~/rak833-loragateway
        $ cd ~/rak833-loragateway
        $ sudo ./install.sh

- You will be see a message like. Reply ‘n’ to the question.

		Gateway configuration:
		Detected EUI B827EBFFFE9BFF6C from eth0
		Do you want to use remote settings file? [y/N]

- Next you will be see message like. Type Enter keep default or enter your information.

		Host name [ttn-gateway]:
		Descriptive name [ttn-rak833]:
		Contact email: 
		Latitude [0]: 
		Longitude [0]: 
		Altitude [0]: 

- If you want to use the remote configuration option, please make sure you have created a JSON file named as your gateway EUI (e.g. `B827EBFFFEXXXXXX.json`) in the [Gateway Remote Config repository](https://github.com/ttn-zh/gateway-remote-config). 
- When the rpi is restarted automatically. You should now have a running gateway in front of you!

# Credits

These scripts are largely based on the awesome work by [Ruud Vlaming](https://github.com/devlaam) on the [Lorank8 installer](https://github.com/Ideetron/Lorank).
