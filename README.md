# Asus Sabertooth X79 with i7 4930k & GTX 1050 Ti Hackintosh

These are just my personal experience re-installing OS X on this machine I initially built for hackintosh 4 years ago.

* i7 4930k
* GTX 1050 Ti
* Asus Sabertooh X79
* Kingston V300 (sv300s37a240g)
* TP-Link tl-wdn4800 n900

Running High Sierra 10.13.6 17G66

Not working:
* AirDrop with iOS (can still AirDrop with newer Macs by searching for older macs on the new mac)

There probably exists better BT + Wifi combo PCI-e cards now.

## Resources
RampageDev's X79 Guide ([mediafire](http://www.mediafire.com/file/pd6v64ym2s9fv6n/X79.dmg/file)) (found through [reddit](https://www.reddit.com/r/hackintosh/comments/9ga0r9/rampagedev_x79_dmg/) since their site seems down)

[Hackintosher's Guide and prepackaged EFI](https://hackintosher.com/guides/high-sierra-install-full-guide/)

[Hackintosher's Nvidia Web Driver guide](https://hackintosher.com/guides/properly-install-nvidia-drivers-high-sierra-10-13/)

[Tekrevue High Sierra installer download guide](https://www.tekrevue.com/tip/download-high-sierra-mojave/)

[Clover Configurator](https://mackie100projects.altervista.org/download-clover-configurator/)

[NativeDisplayBrightness](https://www.reddit.com/r/mac/comments/7wcecq/great_new_fork_of_native_display_brightness_with/)

## Overview
Hackintosher's prepackaged EFI got me all the way through macOS Mojave's install, but the resulting install wouldn't boot. Following RampageDev's guide wouldn't get me all the way through the install. I ended first copying Hackintosher's EFI folder to my USB's EFI partition, then following all of RampageDev's guide (install kexts, SSDT.aml and SSDT-1.aml, config.plist) except the Audio portion, since the existing audio kext works. This combination of kexts supplied by Hackintosher and RampageDev worked. Those are the files in this repo.

Overall, a much easier and simpler install process than my Dec 2014 install on the same machine.

# Nvidia Web Driver
Installed Nvidia Webdriver using `bash <(curl -s https://vulgo.github.io/webdriver) 387.10.10.10.40.113`. Hackintosher's guide suggests enabling / disabling SIP for this; it's not necessary (at least for this build of High Sierra) and actually enabling SIP prevents the webdriver kexts from being properly installed. Initially noticed it seemed to be okay despite Hackintosher's warning based on forum posts. I would leave SIP on 0x3.

# Audio
Works out of the box thanks to the kexts included.
