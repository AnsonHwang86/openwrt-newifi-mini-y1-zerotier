# openwrt-configuration

*Guide to install openwrt on lenovo newifi mini Y1(model: R6830);

*Backup factory bin(option)*
1. power on your Y1, hold on reset button about ten seconds to restore your Y1.

2. connet your Y1's LAN port to PC with RJ45 cable.

3. enter 192.168.99.1 in PC browser, you will enter the administrator page of Y1.

4. the user is root, and the default password is admin.

5. insert your usb disk to Y1's USB port, and make sure it succefully mounted.

6. open putty to ssh your router, in putty, excute the following command to backup the fireware `cd /mnt/sda1` `dd if=/dev/mtd2 of=factory.bin` `dd if =/dev/mtd3 of=fullflash.bin`

![image](https://user-images.githubusercontent.com/16233397/170901576-f23584df-0d65-404b-8037-2fc68be0e082.png)

You will find there are two bin in the usb disk.

Install openwrt

1.download openwrt firmware for Y1, from https://openwrt.org/toh/hwdata/lenovo/lenovo_newifi_mini_y1 , download firmware, you can download snapshot version(without lucci).
  I choice fullversion this time. `openwrt-21.02.3-ramips-mt7620-lenovo_newifi-y1-squashfs-sysupgrade.bin`
  
2.download the breed for Y1, from https://breed.hackpascal.net/ download 'breed-mt7620-lenovo-y1.bin', please be notice there is another breed-mt7620-lenovo-y1s.bin next to it too.

3.download winscp and putty

4.plug your RJ45 cable to Y1's LAN port and PC.

5.power off your Y1, hold on reset button, then power on Y1, wait about 5 second, the led light will blink. 

6.In PC's network setting, change adapter's address to IP:192.168.1.2 subnet mask:255.255.255,Default gateway: 192.168.1.1
  ![image](https://user-images.githubusercontent.com/16233397/170900083-bb3e607c-dda8-41f4-8eaf-c0800cbcae86.png)
  
7.enter browser: 192.168.1.1
![image](https://user-images.githubusercontent.com/16233397/170900293-49ec4abe-fe40-463e-b4a6-6da843c356ca.png)
upload the breed firmware, and submit, wait a minute, the will breed will successfully installed.

8.repeat 5, then 7, you will see the controller console of breed. 

9.choose the openwrt firmware download before. upload and submit it.
![image](https://user-images.githubusercontent.com/16233397/170900638-330b2e33-d5ad-4365-86a0-777a1d68678d.png)

10. the openwrt is installed in your lenovo Y1.

11.change to adapter to `Obtain an IP address automatically`, and enter 192.168.1.1 to broswer, leave password to empty, click login
![image](https://user-images.githubusercontent.com/16233397/170901008-8e402641-8893-4580-b8c9-7f44b7a84781.png)

12.enjoy your openwrt now.

install zerotier on openwrt please find the reference
https://github.com/mwarning/zerotier-openwrt/wiki

Note: if you want to visit device behind router, please don't forget to check the "WAN" in the firewall setting 
![image](https://user-images.githubusercontent.com/16233397/170902170-dcfd2e18-1c23-4e7b-a998-d7052e973b05.png)
