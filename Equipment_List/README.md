# __Equipment List__

Note: In addition to the equipment itself, you will need to purchase a web URL, which as of 2024 costs \~$10/yr. The instructions on how to do so are on the [next page](../Instructions/Cloudflare_(Web_URL).md).

## __Very Basics__

You will need an internet connection, provided by an internet router you own. This process requires making some small modifications to your router which you will only be able to do you if can log in to its internal software. This means you cannot be relying on public college or library wi-fi for your internet connection, or on a phone's data plan.

If you own your own router but do not know how to log into it, [Wikihow has an excellent and easy to follow guide](https://www.wikihow.com/Access-a-Router). You can also call your internet provider to ask for their help logging into your router.

## __Full Home Server with Cloud Storage and Secure Communication__

As of 2024, the following will cost ~$150-200, with $150 for the bare minimum server space (250 GB) and $200 for more comfortable server space (~2 TB). 

#### __Critical Hardware (\~$150-200)__

Buy a [Raspberry Pi 5](https://www.raspberrypi.com/products/raspberry-pi-5/) with at least [2 GB of RAM](https://www.pishop.us/product/raspberry-pi-5-4gb/). I would recommend 4 GB to be safe however. ($50-60)

- A case (like [this](https://www.pishop.us/product/raspberry-pi-case-for-pi-5-red-white/), which includes a cooling fan) ($10)
  - You should also get extra [heatsinks](https://www.pishop.us/product/set-of-heatsinks-for-raspberry-pi-5-4-pack-copper/) ($4)
- A compatible power supply (like [this](https://www.pishop.us/product/raspberry-pi-27w-usb-c-power-supply-white-us/)) ($14)
- A good quality SSD (solid state drive) with at least 1 TB of memory [I (Sengachi) personally use this SSD and it's worked well so far](https://www.amazon.com/Silicon-Power-Performance-Internal-SP002TBSS3A55S25/dp/B07Q37V1C9). High transfer speeds are a plus when considering what SSD card to get, but reliability is the most important thing. Always look up customer reviews from somewhere other than the major sites (like Amazon), which are sometimes faked. ($50-100)
   - At the low end, a full home server can also run off of a very small SSD with 250 GB of memory or less. [This can be very cheap](https://www.amazon.com/SSD-Dogfish-Internal-Performance-Desktop/dp/B07JH934KL), and you can add another SSD later if you find it's too small. ($25)
   - You can also purchase an [NVMe SSD](https://www.pishop.us/product/raspberry-pi-nvme-ssd-256gb). These tend to be a bit more expensive than other SSDs, but take up less space. They can also improve performance if installed via a PCIE port, though this requires a special case and is beyond the scope of this tutorial. If you are an expert, see [this guide](https://raspberrytips.com/use-nvme-ssd-on-raspberry-pi/) on NVMe PCIE installation for details. ($35 for 250 GB)
- An [external SSD enclosure](https://www.amazon.com/UGREEN-External-Enclosure-Housing-Adapter/dp/B076WQHK2G) to connect your SSD to your Pi, with a USB 3.0 connector, and which **runs off its own power adapter**. This is very important. Your enclosure should come with its own power adapter. It will be visible in shopping pictures, and have a wall outlet plug. Many external SSD enclosures do not have this and operate off of power from your computer, via the USB 3.0 connector; the Pi 5 **does not have enough power** to do this. ($30)
  - If you use an NVMe SSD, you will need a [special enclosure like this](https://www.amazon.com/SSK-Aluminum-Enclosure-Adapter-External/dp/B07MNFH1PX). One advantage of NVMe SSDs is that they require less power and do not need a wall outlet plug, and can be power via their USB connection with your Raspberry Pi. ($20) 
- [An ethernet cable](https://www.homedepot.com/p/Commercial-Electric-CE-15-ft-Cat-6A-UTP-Patch-Cable-White-5615-WH-VN/328470762). Make sure this is long enough to stretch from your router to your equipment. ($10-20)

Raspberry Pi 5 and SSD in an external enclosure. (left) Exposed Pi 5 and SSD. (Right) Enclosed Pi 5 and SSD.
<img src="../Media_Repository/Raspberry_Pi_5_and_SSD_exposed.jpg" alt="Exposed Pi 5 and SSD" title="Exposed Pi 5 and SSD" width="40%"/> <img src="../Media_Repository/Raspberry_Pi_5_and_SSD_enclosed.jpg" alt="Enclosed Pi 5 and SSD" title="Enclosed Pi 5 and SSD" width="40%"/> 

## __Secure Communication Only__

As of 2024, the following will cost $50-70. 

#### __Critical Hardware (\~$50)__

Buy a [Raspberry Pi Zero 2 W](https://www.raspberrypi.com/products/raspberry-pi-zero-2-w/). ($15)

- A case (like [this](https://www.pishop.us/product/aluminum-alloy-protection-case-for-raspberry-pi-zero-series-fits-zero-zero-2-w/)) ($9)
  - You may also need an extra [heatsink](https://www.pishop.us/product/aluminum-heatsink-for-raspberry-pi-zero/) if your case does not have metal heatsink ridges (rectangular ridges which dissipate heat) and come with thermal putty contacts. (The case above does not need an extra heatsink.) ($2)
- A compatible power supply (like [this](https://www.pishop.us/product/wall-adapter-power-supply-micro-usb-2-4a-5-25v/)) ($8)
- A high quality micro SD card with at least 8 GB of space (the [official Raspberry Pi Micro SD cards with 32 GB](https://www.pishop.us/product/raspberry-pi-sd-card-32gb/) are high quality and will serve well, note that it also comes with a Micro SD to SD card adapter) ($11)
 - Note: Do not get a very large SD Card (256+ GB) for more storage. SD Cards do not survive constant file transfers the way SSDs (solid state drives) do and using massive ones for moving and storing many files is prone to failure.

Raspberry Pi Zero 2 W. (left) Bare motherboard. (Middle) Motherboard with thermal putty contacts, which help conduct heat away from the board and into the case. (Right) Pi Zero 2 W fully enclosed in case, with an extra unneeded aluminum heatsink on top. 

<img src="../Media_Repository/Raspberry_Pi_Zero_2_W_0-Bare.jpg" alt="Bare Raspberry Pi Zero 2 W motherboard" title="Bare Raspberry Pi Zero 2 W motherboard" width="30%"/> <img src="../Media_Repository/Raspberry_Pi_Zero_2_W_1-With-Thermal-Patches.jpg" alt="Raspberry Pi Zero 2 W motherboard and thermal putty contacts" title="Raspberry Pi Zero 2 W motherboard and thermal putty contacts" width="30%"/> <img src="../Media_Repository/Raspberry_Pi_Zero_2_W_2-With-Case.jpg" alt="Raspberry Pi Zero 2 W in case" title="Raspberry Pi Zero 2 W in case" width="30%"/>

#### __Optional Hardware__

- Ethernet to micro USB port (like [this](https://www.amazon.com/Smays-Micro-B-Ethernet-compatible-Raspberry/dp/B01AT4C3KQ)) ($15)
  - This will allow you to use wired ethernet rather than wireless wifi. This allows for faster and more consistent connection.
- SD Card USB Adapter (like [this](https://www.amazon.com/Reader-Adapter-Camera-Memory-Wansurs/dp/B0B9QZ4W4Y)) ($5)
  - If your computer does not have an SD card or micro SD card reader, you will need one of these.
 
# __Next Step__

Once you have finished your purchases, you will need to purchase a web URL, which as of 2024 costs \~$10/yr. [Follow the instructions here to do so](../Instructions/Cloudflare_(Web_URL).md).
