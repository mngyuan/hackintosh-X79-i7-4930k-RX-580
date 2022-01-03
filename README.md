# Asus Sabertooth X79 with i7 4930k & RX 570 Hackintosh

I updated this machine to Catalina directly from High Sierra and had to swap the 1050 Ti for an RX 570.

Hardware
* i7 4930k
* MSI RX 570 OC
* Asus Sabertooh X79
* Kingston V300 (sv300s37a240g)
* TP-Link tl-wdn4800 n900
* Sabrent BT-UB40

Running High Sierra 10.15.6, SMBIOS system definition MacPro6,1

Working
* Audio
* iMessage
* Bluetooth/WiFi/Ethernet
* Dual monitors
* Sleep

Not working
* Airdrop

## Resources
[Guide on updating hackintosh](https://davejansen.com/keeping-your-hackintosh-up-to-date/)

[Vanilla Hackintosh Guide from /r/hackintosh](https://hackintosh.gitbook.io/-r-hackintosh-vanilla-desktop-guide/)

[Kext Updater Tool](https://bitbucket.org/profdrluigi/kextupdater/downloads/)

[IO80211Family.kext for TP-Link tl-wdn4800 n900](https://www.tonymacx86.com/threads/solved-my-wifi-tl-wdn4800-n900-not-working-after-install-mojave.257115/)

[RX 580 HDMI port fix](https://www.tonymacx86.com/threads/solved-sapphire-rx-580-nitro-se-black-screen-on-hdmi-and-dvi.267078/page-4#post-1906898)


## Overview
This time around, hackintoshing has matured a lot, even in the last 1.5 years since I reinstalled High Sierra on this machine, and updating was much simpler than a clean install.

1. Removed `nvda_drv=1` from boot options
1. Removed `NvidiaWeb` from `SystemParameters`
1. Updated Clover through Clover Configurator
   * I'm using UEFI so I had to check the `Install Clover to UEFI only` option
   * Using list of kexts in `/EFI/CLOVER/kexts/Other`, checked kexts I needed in the installer
1. Updated kexts through Kext Updater Tool
1. Installed Catalina (through App Store)
1. Installed `IO80211Family.kext` to get wifi
1. Downgraded `IntelMausiEthernet.kext` back to 2.2.0 to get ethernet working again
1. Applied above  [RX 580 HDMI port fix](https://www.tonymacx86.com/threads/solved-sapphire-rx-580-nitro-se-black-screen-on-hdmi-and-dvi.267078/page-4#post-1906898) to get proper displaysleep, HDMI ports working
1. Modified energy saver to prevent sleep

## Notes
I'm using a RX580 fix because previously this machine had a Sapphire Pulse RX 580 installed, but it was causing the PSU to trip.

I'm using [the orange icon fix](https://www.tonymacx86.com/threads/small-question-yellow-disk-image-icons-at-desktop.174907/post-1119847) to fix internal drives showing as external drives.
