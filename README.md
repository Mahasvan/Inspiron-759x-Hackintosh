# Inspiron-759x-Hackintosh
This repository is for people who want macOS on their Inspiron 759x laptops.
In this repo, I am only using OpenCore, as Clover is basically a frankenstein bootloader these days


### Specs:
 - Intel Core i7 9750H
 - 16GB DDR4 2666Mhz
 - GTX 1050 (disabled via SSDT)
 - Intel AC9560 Wifi+BT

## Note: This repo is ONLY FOR REFERENCE

DO NOT use this EFI as it is. It probably won't boot, and I am not responsible for any damage that occurs.

Follow the [Opencore Install Guide](https://dortania.github.io/OpenCore-Install-Guide/) to make your EFI.

With that said, let's get on with what each SSDT and Kext does

### SSDTs

![List of SSDTs needed](https://user-images.githubusercontent.com/82939599/121011440-3d373100-c7b4-11eb-8ec6-759913df5aba.png)

The SSDTs mentioned in this screenshot are prebuilt. These are all the SSDTs you need to boot into the macOS installer.
Note that you don't see SSDT-XOSI in my ACPI folder because I have replaced it with SSDT-GPIO. I cannot guarantee it will work, so it is better to use SSDT-XOSI along with the ACPI rename, as the guide says.

### Kexts

The kexts mentioned in the dortania guide are all that are needed to boot. However, there are some kexts that offer extra features. These are recommended for post-install.
Note: You might also need CpuTscSync if your booting process gets stuck. (I need it, so I included it in the kexts folder)

CPUFriend: Facilitates proper CPU Power management. Needs another kext CPUFriendDataProvider, which we can make ourselves by following the post install guide.

NoTouchID.kext: Fingerprint sensors in Inspiron Laptops have no way of working in macOS. So we use this kext

BrightnessKeys.kext Facilitates automatic handling of brightness keys without acpi modification

VirtualSMC Plugins:
 - SMCProcessor
 - SMCSuperIO
 - SMCDellSensors
 - SMCBatteryManager

VoodooI2C + VoodooI2cHID: Needed for trackpad functioning. 

Sinetek-rtsx.kext: Used for enabling the fingerprint sensor. Note that this may not work on your machine, and should be used with caution.

### Screenshots

![Screen Shot 2021-03-27 at 10 25 30 PM](https://user-images.githubusercontent.com/82939599/121173361-5dc7bf80-c876-11eb-8eed-fabf857cd34c.png)

![geekbench mac](https://user-images.githubusercontent.com/82939599/121173170-1b9e7e00-c876-11eb-8299-c8b661b73176.png)


#### Troubleshooting

Even though you followed the Dortania guide correctly, there are bound to be errors. There is a Hackintosh community, where you can discuss and solve problems.
r/Hackintosh discord server: https://discord.gg/u8V7N5C
r/Hackintosh Subreddit: https://www.reddit.com/r/hackintosh/
