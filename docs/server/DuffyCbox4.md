# Installing Ubuntu 20.04 Server in Asus Chromebox 4

## Resources

- [https://mrchromebox.tech/](https://mrchromebox.tech/)

## Introduction

I scored a cool Asus ChromeBox 4 Duffy (i3 10th generation, 8GB RAM and, 60 GB SSD) for quite a cheap price with the 
intentions of transforming it into a home server. My only issues is with its specs are the low SSD capacity but I have
in mind implementing a NAS setup sometime in the future. This should be enough to host all my tinkering for a while.

## Issues

I intended to convert my Box into a server not knowing exactly where I was going. ChromeOS by default has a 
write protection flag for the firmware which does not allow us to boot from other sources than the intended one. 
This means you can not boot your shiny new OS directly from a USB stick.

I have 2 solutions to bypass this protection:
- Legacy boot mode
- Disabling the Write Protection flag

You can find [here](https://mrchromebox.tech/#devices) what options your device has. 

The primary recommendation is to disable the WP flag as it allows you to automatically boot 
from your desired OS. Also, for older versions of ChromBox booting in Legacy mode may not be supported.

For newer versions Legacy boot mode should be supported and disabling the WP is more difficult as it requires 
[special hardware](https://chromium.googlesource.com/chromiumos/third_party/hdctools/+/HEAD/docs/ccd.md#SuzyQ-SuzyQable).

Google has implemented a new way to remove the WP flag that involves a **Suzy-Q cable**. This is a USB-A to USB-C 
cable with modified wiring that allows the device for developer uses. 

As I don't have this cable at the moment, and I wanted a quick set-up Legacy boot mode it is.

## Add legacy flag and implement legacy boot mode

I'm  not going to explain it better than in MrChromebox blog so [here is the link](https://mrchromebox.tech/#bootmodes). 

Just as a quick recap:

1. Start-up as recovery mode (Use a sim card remover tool)
2. Start-up as developer mode (It is going to take a while to boot as it removes everything)
3. Access the shell in developer mode 
4. Run the [utility script](https://mrchromebox.tech/#fwscript) found in MrChromebox page
5. Start-up normally and press *Ctrl+L*

## Booting an Ubuntu image

Select in the bios page booting from a USB and install your shiny new OS!

**As said previously, Legacy booting mode is not going to be initiated automatically. This means that if the server 
shuts down for whatever reason, CTRL+L need to be press to initiate this boot mode again.**