To-do: 
Secure communication only section, with dietpi.

[<- Prev](../Instructions/Raspberry_Pi_Assembly.md) [Next ->](../Instructions/SSH_setup.md) 
 
# __Full Home Server__

### __Surge Protection__

For the safety of your electronics, we highly recommend that all power outlets you plug your equipment to are part of surge protector, or a power strip with surge protection, to avoid losing your equipment and data to a power surge.

### __Troubleshooting__

When something goes wrong in this section, or the following SSH_Setup and CasaOS_Setup sections, diagnosing the issue can often be tricky. If this happens, we suggest restarting the process from this point. Unplug your Raspberry Pi and disconnect your SSD from it. Restart the process from this point.

1. Install the [Raspberry Pi Imager](../Software_Repository/Raspberry_Pi_Imager.md) on your computer. This lets you turn your Raspbbery Pi from a lump of silicon into a working computer you can talk to.

2. Slot your SSD into your external SSD enclosure, then plug the enclosure's power supply into a power outlet, then plug the enclosure's USB 3.0 cable into your computer. 

<img src="../Media_Repository/SSD_exposed.jpg" alt="SSD exposed" title="SSD exposed" width="30%"/> <img src="../Media_Repository/SSD_enclosed.jpg" alt="SSD enclosed" title="SSD enclosed" width="30%"/> 

3. Open up the Raspberry Pi Imager on your computer.

<img src="../Media_Repository/Pi_Imager_search.png" alt="Searching for Pi imager" title="Searching for Pi imager" width="30%"/> <img src="../Media_Repository/Pi_Imager_landing_page.png" alt="Pi imager landing page" title="Pi imager landing page" width="30%"/> 

4. For `Raspberry Pi Device` select 'Raspberry Pi 5'. For `Choose OS`, select 'Raspberry Pi OS (other)' and then 'Raspberry Pi OS Lite (64 bit)'. For 'Storage' select the SSD you have plugged in. This should be the only device which shows up unless you have other external storage devices plugged in.

**CAUTION:** Be careful that you select 'Raspberry Pi OS Lite *(64 bit)*', and do not select 'Raspberry Pi OS Lite *(32 bit)*'.

<img src="../Media_Repository/Pi_Imager_OS_Other.png" alt="Pi imager OS other" alt="Pi imager OS other" title="Pi imager OS other" width="30%"/> <img src="../Media_Repository/Pi_Imager_OS_Lite.png" alt="Pi imager OS lite" title="Pi imager OS lite" width="30%"/> <img src="../Media_Repository/Pi_Imager_OS_Complete.png" alt="Pi imager OS complete" title="Pi imager OS complete" width="30%"/> 

5. Click `Next` and then `Edit Settings`. Fill in the settings. **Keep track of your Pi hostname, your Pi username (if different), and your Pi password!!!** These are very important. The Pi hostname will be used to connect to your Pi. The Pi username and password will be used to give commands to your Pi. **Be careful about entering your Pi password. There is no way to tell if you did this wrong.**

If and ***only if*** you are going to be using a wireless connection for your Raspberry Pi, with no Ethernet connection, should you perform Step 6. If you will be using an Ethernet connection for your Raspberry Pi, uncheck the box next to `Configure Wireless LAN` instead.

6. Under `Wireless LAN`, for `SSID`, enter the name of your wifi. Under `Wireless LAN`, for `SSID`, enter your wifi password. Click the `Services` tab and make sure you have 'Enable SSH' and 'Use password authentication' enabled. This will ensure you can talk to your Pi through your wifi. Click `Save`, `Yes`, and `Yes`. Wait for the Raspberry Pi Imager to finish writing the Pi OS to your SSD. If your computer asks you if you want to format your device when finished **do not say yes** (this will wipe your Pi device). 

<img src="../Media_Repository/Pi_Imager_OS_settings_1.png" alt="Pi imager OS other" alt="Pi imager OS settings" title="Pi imager OS settings" width="30%"/> <img src="../Media_Repository/Pi_Imager_OS_settings_2.png" alt="Pi imager OS settings" title="Pi imager OS settings" width="30%"/> 

7.
  - Remove the USB plug of the SSD enclosure from your computer.
  - Make sure your Pi is unplugged from any power outlet.
  - Plug the USB plug of the SSD enclosure into the Pi.
  - Plug your SSD enclosure's power outlet into a power outlet.
  - Plug your Pi into a power outlet.
  - Wait a few minutes while your Pi boots up for the first time.
 
# __Next Step__

You now have a tiny functioning computer! Your next step is to connect to it.

[<- Prev](../Instructions/Raspberry_Pi_Assembly.md) [Next ->](../Instructions/SSH_setup.md) 
