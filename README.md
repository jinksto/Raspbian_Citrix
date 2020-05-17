# Raspbian_Citrix
Instructions for configuring a Raspberry Pi 4 (2GB) to work with the Citrix ICA client (icaclient_20.04.0.21_armhf.deb).

JINKSTO: most of my repo is private because things that I say don't represent the views of my employer.  If you want access to a specific repo send me a DM via the usually places.

# Background
Someone on the team thought it'd be fun if we could get a thin-client connection working on Raspbian.  I spent a lot of time putting it together and working out the finicky bits.  However, with the latest versions of Raspbian and Citrix Workstation it's really very straight forward and can be done with very little trouble. 

# Instructions

###### Install Raspbian
1. Download Raspbian latest desktop https://downloads.raspberrypi.org/raspbian_latest
1. Burn to card with Raspberry Pi Imager: https://downloads.raspberrypi.org/imager/imager.exe 
      This is new but seems to work though slower than win32DiskImager. Also, obviates the need to pre-download the image. 
1. Once burned, insert the card into your RPI, boot, configure networking, etc as you like.  


###### Install ICA
1. DownloadCitrix "Workspace app for Linux (ARM HF)" deb package  from https://www.citrix.com/downloads/workspace-app/linux/workspace-app-for-linux-latest.html
1. Open Terminal

```bash
      $cd ~/Downloads
      $sudo apt update
      $sudo apt upgrade
      $sudo dpkg -i ./icaclient_20.04.0.21_armhf.deb
      $sudo apt update
      $sudo apt upgrade
      $sudo mv  /opt/Citrix/ICAClient/keystore/cacerts /opt/Citrix/ICAClient/keystore/cacerts_bk
      $sudo ln -s /etc/ssl/certs/  /opt/Citrix/ICAClient/keystore/cacerts
```

###### Go!
1. From the desktop open your web browser and go to your F5 login portal.
1. Login as you normally would
1. Click the device you want to open
1. Doubleclick the downloaded `launch.ica` 

###### Contact
Ping jinksto via the usual methods 
   


    

