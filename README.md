![image](https://user-images.githubusercontent.com/85907829/213875902-b6f091a8-61c4-40ab-982f-45621d817f4a.png)

ASUS TUF X570-PLUS, (WIFI) RYZEN 9 5900X, RX 6600, Hackintosh EFI


Things that work (Ventura)
------------------
Everything
------------------
Things that don't work
------------------------
DRM in safari,
Apple music,
AppleTV+,
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

[Download the EFI (Ventura)](https://github.com/bnunowo/Hackintosh/tree/ventura)

------------------------------------
Disable
Fast Boot
Secure Boot
Serial/COM Port
Parallel Port
Compatibility Support Module (CSM) (Must be off in most cases, GPU errors/stalls like gIO are common when this option is enabled)
IOMMU
Special note for 3990X users: macOS currently does not support more than 64 threads in the kernel, and so will kernel panic if it sees more. The 3990X CPU has 128 threads total and so requires half of that disabled. We recommend disabling hyper threading in the BIOS for these situations.

#Enable
Above 4G Decoding (This must be on, if you can't find the option then add npci=0x3000 to boot-args. Do not have both this option and npci enabled at the same time.)
If you are on a Gigabyte/Aorus or an AsRock motherboard, enabling this option may break certain drivers(ie. Ethernet) and/or boot failures on other OSes, if it does happen then disable this option and opt for npci instead
2020+ BIOS Notes: When enabling Above4G, Resizable BAR Support may become an available on some X570 and newer motherboards. Please ensure that Booter -> Quirks -> ResizeAppleGpuBars is set to 0 if this is enabled.
EHCI/XHCI Hand-off
OS type: Windows 8.1/10 UEFI Mode (some motherboards may require "Other OS" instead)
SATA Mode: AHCI
