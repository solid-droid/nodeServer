# Install OS headless
1. download Raspberry Pi OS Lite [here](https://www.raspberrypi.com/software/operating-systems/) 
   > [tested version](https://downloads.raspberrypi.org/raspios_oldstable_armhf/images/raspios_oldstable_armhf-2022-01-28/2022-01-28-raspios-buster-armhf.zip)
3. format 16GB sd card using [raspberry pi imager](https://www.raspberrypi.com/software/)
4. upload to OS to sd card using [Etcher](https://www.balena.io/etcher/) or [raspberry pi imager](https://www.raspberrypi.com/software/)
5. add "ssh" file to sdcard root
6. add "wpa_supplicant.conf" file to sdcard root and add the following to it.
```bash
country=AU
ctrl_interface=DIR=/var/run/wpa_supplicant GROUP=netdev
update_config=1
network={
	ssid="MyWiFiNetwork"
	psk="aVeryStrongPassword"
	key_mgmt=WPA-PSK
}
```

# Connect to raspberry pi zero w via putty
1. wait for sometime (bootup time)
2. Open putty in SSH (default is SSH)
3. type pi@raspberrypi.local and connect with password : raspberry
4. if not working use [angry ip scanner](https://angryip.org/download/#windows) to find ip and try with that
![image](https://user-images.githubusercontent.com/32586986/162153764-c0d1c6f3-bf14-4ea7-be25-c81439af0982.png)
![image](https://user-images.githubusercontent.com/32586986/162153889-e3f3148a-856f-4072-b774-2c6dbfc41136.png)
6. if raspberry pi not showing in the list => either your SSID / pwd is wrong or some issue with os / your device.

# Setting up environment
Update environment => [source](https://jamesjdavis.medium.com/how-to-update-raspberry-pi-just-follow-these-easy-steps-ac507cf70238#:~:text=To%20update%20the%20Raspberry%20Pi,Raspberry%20Pi's%20library%20of%20applications.)
```bash
sudo apt update
sudo apt upgrade
sudo reboot
```
Installing Nodejs 
```bash
sudo apt-get install nodejs
sudo npm install -g npm
sudo ln -s /usr/bin/nodejs /usr/local/bin/node nodes711.com
sudo reboot
```
or => [source](https://hassancorrigan.com/blog/install-nodejs-on-a-raspberry-pi-zero/)
```bash
wget https://unofficial-builds.nodejs.org/download/release/v14.13.0/node-v14.13.0-linux-armv6l.tar.xz
tar xvfJ node-v14.13.0-linux-armv6l.tar.xz
sudo cp -R node-v14.13.0-linux-armv6l/* /usr/local
rm -rf node-*
sudo reboot
node -v && npm -v
```

Installin tmux (for multitasking)
```bash
sudo apt install tmux
```
 
 Using Github
 ```bash
 sudo apt install git
 git --version
 ```
 Make repo folder
 ```bash
 cd /
 ls
 mkdir repo
 ls
 cd repo
 ```
 clone your repo
 ```
 git clone <repoUrl https>
 ```
 if u get permision denied error
 ```bash
 sudo chmod -R 777 /<path of directory>
 ```
