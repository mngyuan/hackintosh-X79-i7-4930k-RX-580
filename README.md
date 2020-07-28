# Asus Sabertooth X79 with i7 4930k & RX 580 Hackintosh

I updated this machine to Catalina directly from High Sierra and had to swap the 1050 Ti for an RX 580.

Hardware
* i7 4930k
* Sapphire Pulse RX 580
* Asus Sabertooh X79
* Kingston V300 (sv300s37a240g)
* TP-Link tl-wdn4800 n900

Running High Sierra 10.15.6, SMBIOS system definition MacPro6,1

Working
* Audio
* iMessage
* Bluetooth/WiFi/Ethernet
* Dual monitors (with DisplayPort)

Not working
* Airdrop (haven't debugged yet)
* HDMI ports on RX 580

## Resources
[RampageDev's X79 Guide](X79.dmg) ([mediafire mirror](http://www.mediafire.com/file/pd6v64ym2s9fv6n/X79.dmg/file)) (found through [reddit](https://www.reddit.com/r/hackintosh/comments/9ga0r9/rampagedev_x79_dmg/) since their site seems down)

[Hackintosher's Guide and prepackaged EFI](https://hackintosher.com/guides/high-sierra-install-full-guide/)

[Vanilla Hackintosh Guide from /r/hackintosh](https://hackintosh.gitbook.io/-r-hackintosh-vanilla-desktop-guide/)

[Kext Updater Tool](https://bitbucket.org/profdrluigi/kextupdater/downloads/)

[IO80211Family.kext for TP-Link tl-wdn4800 n900](https://www.tonymacx86.com/threads/solved-my-wifi-tl-wdn4800-n900-not-working-after-install-mojave.257115/)

[Guide on updating hackintosh](https://davejansen.com/keeping-your-hackintosh-up-to-date/)

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
1. Swapped HDMI cable for DisplayPort on second monitor to get it working again
