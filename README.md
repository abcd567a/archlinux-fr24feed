# Archlinux-fr24feed ver 1.0.44-0

### Install Flightradar24's Data Feeder on Arch Linux OS on: <br> (1) PC & Laptop: amd64, x86_64, i386  </br> (2) Raspberry PI and other SBC: armhf, armv7 arm64, aarch64, armv8 </br>

### Issue following 3 commands, and fr24feed will be installed on your Computer / Pi </br>

```
git clone https://github.com/abcd567a/archlinux-fr24feed
```
```
cd archlinux-fr24feed
```
```
makepkg -si
```

### When installation is completed, issue following commands to signup  </br>

```
sudo fr24feed --signup
```
```
sudo systemctl restart fr24feed
```
#### To check status:
```
sudo systemctl status fr24feed  

sudo fr24feed-status
```

</br>
