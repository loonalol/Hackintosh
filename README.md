
ASUS TUF X570-PLUS, (WIFI) RYZEN 9 5900X, RX 6600, Hackintosh EFI


Things that work
------------------
Everything
-------------------
Things that don't work
------------------------
DRM in safari, 
DRM in apple music,
DRM in AppleTV+,
SLEEP MODE REQUIRES REBOOT
---------------------------


Insatlation Windows:

Format your USB via rufus

![image](https://user-images.githubusercontent.com/85907829/213874618-554025e6-a5a6-4d16-86f8-64bfa3d2a93e.png)

Download https://github.com/acidanthera/OpenCorePkg/releases  (opens new window) and head to /Utilities/macrecovery/. Next, click next to the current folder path and type cmd to open a Command Prompt in the current directory:
![image](https://user-images.githubusercontent.com/85907829/213874839-82df2927-fa00-44ab-a892-ad92232e862f.png)
Now run one of the following depending on what version of macOS you want(Note these scripts rely on Python 3 (opens new window) support, please install if you haven't already):

#
Monterey (12)
python3 macrecovery.py -b Mac-FFE5EF870D7BA81A -m 00000000000000000 download

Latest version
ie. Ventura (13)
python3 macrecovery.py -b Mac-4B682C642B45593E -m 00000000000000000 download
#

This will take some time, however once you're finished you should get either BaseSystem or RecoveryImage files:
![image](https://user-images.githubusercontent.com/85907829/213874901-e087e7dc-b352-4bd3-9034-ea7323f9e5d3.png)

Copy and paste the com.apple.recovery.boot to your USB

Download the EFI


``
