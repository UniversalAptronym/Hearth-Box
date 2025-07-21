# __Cloudflared Tunnel Setup (Connecting Your Pi To The Worldwide Web)__

In this section you will install a Cloudflared tunnel. This well let you and others connect securely to your Hearth Box from the worldwide web.

*Author's Note: Tail Scale and Head Scale are programs which can be used in place of Cloudflare for this, removing even that reliance on a potentially untrusted service provide, and we intend to add tutorial options for them at a later date. However these programs are a bit more technically tricky to set up, and morever require technical effort on the part of everyone who wants to connect to your server beyond simply typing in a URL and logging on to your server, so they are not our focus at this time.* 

## __Installing Cloudflared__

Cloudflared (note the 'd') is a program which connects your server to a Cloudflare tunnel. This ensures that encrypted information always goes through Cloudflare, where it is properly encrypted and protected from eavesdroppers. [Here is an explanation, if you are curious.](https://developers.cloudflare.com/cloudflare-one/connections/connect-networks/)

1. If you do not already have it open, access your Raspberry Pi by entering its **local IP address** into your web browser. Open the `App Store` button. Navigate to the "Cloudflared" installer either by scrolling down, or typing `cloudlflared` into the search bar. Then click `Install`.
- In rare cases the default Developer apps are absent due to a mismatch between the date-time on your Pi and the CasaOS servers. If this happens, use PuTTY to reopen the command terminal, then type in `sudo timedatectl set-ntp off` and press Enter. Then type `sudo timedatectl set-ntp on` and press Enter. This resets your Pi's date-time. Then type `sudo systemctl reboot` to restart your Pi.

<img src="../Media_Repository/Cloudflared_Install_1.png" alt="Cloudflared Proxy Manager installation 1" title="Cloudflared Proxy Manager installation 1" width="40%"/> <img src="../Media_Repository/Cloudflared_Install_2.png" alt="Cloudflared Proxy Manager installation 2" title="Cloudflared Proxy Manager installation 2" width="40%"/> 

2. This should bring up the following installation window, which you can scroll to see the entirety of. If it does not, scroll over the "Cloudflared" App and click the three dots which appear, then click Settings. Add your **Raspberry Pi's local IP address** to the leftmost text box under "Web UI". The click `Save`. This tells your server that you want to connect to this program via your local router, not the worldwide web. (You will only be able to access this program from a machine connected to your local router, but that's fine, you only need to use it once.

<img src="../Media_Repository/Cloudflared_Alt_Settings.png" alt="Cloudflared Proxy Manager installation alt settings access" title="Cloudflared Proxy Manager alt settings access" width="30%"/> 
<img src="../Media_Repository/Cloudflared_Install_3.png" alt="Cloudflared Proxy Manager installation 3" title="Cloudflared Proxy Manager installation 3" width="50%"/>

Leave this webpage open in the background during the next steps, you will be returning to it shortly.

## __Setting up a Cloudflare Tunnel__

Next, you will set up a "tunnel" through Cloudflare, for Cloudflared (note the 'd') to connect to. This ensures that encrypted information always goes through Cloudflare, where it is properly encrypted and protected from eavesdroppers. [An explanation, if you are curious.](https://developers.cloudflare.com/cloudflare-one/connections/connect-networks/)

3. If you still have Cloudflare's webpage open from previous steps, return to it. If not, open [Cloudflare's website](https://dash.cloudflare.com/) in a new browser tab or browser page. Return to Cloudflare's `Account Home`.

4. On the left-hand side of your screen, click `Zero Trust`. This will take you to a screen where you enter a team name. Enter whatever you want, you don't have to record this.

<img src="../Media_Repository/Cloudflare_Zero_Trust_1.png" alt="Cloudflare Networks button" title="Cloudflare Networks button" width="40%"/> <img src="../Media_Repository/Cloudflare_Zero_Trust_1a.png" alt="Cloudflare Team Name" title="Cloudflare Team Name" width="30%"/> 

5. In the home page for `Zero Trust`, click `Networks`, then click `Create a tunnel`. Select `Cloudflared`. Enter a name for your tunnel and click `Save Tunnel`. You do not have to record this name - it will be here on your Cloudflare account if you ever need it again. Select `Docker`. Click the text which begins with `$ docker run`, or highlight and press `Ctrl + C` to *Copy* that text.

<img src="../Media_Repository/Cloudflare_Zero_Trust_2.png" alt="Cloudflare tunnel button" title="Cloudflare tunnel button" width="40%"/> <img src="../Media_Repository/Cloudflare_Zero_Trust_3.png" alt="Cloudflare Cloudflared button" title="Cloudflare Cloudflared button" width="40%"/>

<img src="../Media_Repository/Cloudflare_Zero_Trust_4.png" alt="Cloudflare tunnel name field" title="Cloudflare tunnel name field" width="40%"/> <img src="../Media_Repository/Cloudflare_Zero_Trust_5.png" alt="Cloudflare connector text" title="Cloudflare connector text" width="40%"/>

## __Connecting Your Cloudflare Tunnel to Cloudflared__

6. Return to the webpage from Step 1, where you accessed your Raspberry Pi by entering its **local IP address** into your web browser.

7. Click the `Cloudflared` program icon. This will open a new tab with your Cloudflared program. Click inside the text box beneath **Enter Tunnel Connector Token:". Then press `CTRL + V` (for Linux or Windows) or `CMD + V` (for Mac) to *Paste* the text from Step 5.

<img src="../Media_Repository/Cloudflared_Install_4.png" alt="Cloudflared Proxy Manager installation 4" title="Cloudflared Proxy Manager installation 4" width="40%"/> <img src="../Media_Repository/Cloudflared_Install_5.png" alt="Cloudflared Proxy Manager installation 5" title="Cloudflared Proxy Manager installation 5" width="40%"/>

5. Press the `Save` button. It will turn into `Start` button. Press the `Start` button. Close out of the Cloudflared tab and delete `Cloudflared_Tunnel.txt`.

<img src="../Media_Repository/Cloudflared_Install_5.png" alt="Cloudflared Proxy Manager installation 5" title="Cloudflared Proxy Manager installation 5" width="40%"/> <img src="../Media_Repository/Cloudflared_Install_6.png" alt="Cloudflared Proxy Manager installation 6" title="Cloudflared Proxy Manager installation 6" width="40%"/>

That's it! That's all you have to do with Cloudflared.

Note: If you ever move / get a new router, you may have to refresh your token. Do so by returning to the Tunnel page (see the [Cloudflare section](../Instructions/Cloudflare_(Web_URL).md)), clicking the **3 menu dots** next to your tunnel, clicking **Configure**, clicking **Docker**, and then clicking **Refresh Token**. Then copy the new token, as previously, and open Cloudflared. Press **Stop**, paste the new token, then press **Save** and then **Start**.

## __Setting Up Connections To Specific Programs__

6. Finally, return to the Cloudflare webpage, scroll down, and click `Next` at the bottom of the page. This will take you to the page pictured below.
  
**Note:** You will return to this page multiple times. Depending on what part of the process you're at, the `Save` button will either say `Save Tunnel` or `Save Hostname`.

<img src="../Media_Repository/Cloudflare_Public_Hostname_0.png" alt="Cloudflare Public Hostname Blank" title="Cloudflare Public Hostname Blank" width="50%"/>

What you do next depends on whether you are setting up a full home server or only a secure communications hub. Follow the instructions below based on your choice. Either way, this next step will set up a series of sub-websites which you will use to access various functions of your Raspberry Pi. For example, `databag.[exampleweburl].org` will take you to your secure communications hub. Meanwhile `nginx.[exampleweburl].org` will take you to part of your device's security interface, and `pihole.[exampleweburl].org` will take you to the control panel for an adblocker which will reduce the number of ads for all devices on your internet.

### __Raspberry Pi Homepage__

This will take you to your Raspberry Pi homepage, the same webpage you accessed in Step 1 by entering your **Raspberry Pi's local IP address**, but it will do so from anywhere in the world.

In the "subdomain" section, enter **nextcloud**. In the "domain" section, select your chosen URL from the drop-down list. Under "type" select `HTTP`. Under "URL", enter your **Raspberry Pi's local IP address** followed by `:80`. It should have the form: `XXX.XXX.XXX.XXX:80`. Click `Save`. Then select your tunnel name to enter the next public hostname.

<img src="../Media_Repository/Cloudflare_Public_Hostname_homepage.png" alt="Cloudflare Public Hostname Homepage" title="Cloudflare Public Hostname Homepage" width="40%"/> <img src="../Media_Repository/Cloudflare_Tunnel_Select.png" alt="Cloudflare Tunnel Select" title="Cloudflare Tunnel Select" width="50%"/> 

Note: ":80" represents the standard internet "port" which webpages use for unencrypted "http" communications. This does not mean you are connecting to your Raspberry Pi in an insecure way though - this unencrypted communication is only occuring locally between your Cloudflared program and the rest of your Raspberry Pi. All private information is still encrypted properly through Cloudflared. [Here is an explanation about internet ports, if you are curious.](https://www.cloudflare.com/learning/network-layer/what-is-a-computer-port/)

### __Nextcloud__

Once your system is set up, this URL will take you to your new cloud server, which will host a communication hub and cloud storage system where you can back up and share files.

In the "subdomain" section, enter **nextcloud**. In the "domain" section, select your chosen URL from the drop-down list. Under "type" select `HTTP`. Under "URL", enter your **Raspberry Pi's local IP address** followed by `:7580`. It should have the form: `XXX.XXX.XXX.XXX:7580`. Click `Save`. Then select your tunnel name to enter the next public hostname.

<img src="../Media_Repository/Cloudflare_Public_Hostname_nextcloud.png" alt="Cloudflare Public Hostname Nextcloud" title="Cloudflare Public Hostname Nextcloud" width="40%"/> <img src="../Media_Repository/Cloudflare_Tunnel_Select.png" alt="Cloudflare Tunnel Select" title="Cloudflare Tunnel Select" width="50%"/> 

Note: Technically you can use any open port number for Nextcloud, not just ":7580". However, ":7580" is selected to match the port we will designate for Nextcloud in a later step. Do not change this number unless you know what you're doing.

### __Databag__

Once your system is set up, this URL will take you to a secondary secure communication hub.

In the "subdomain" section, enter **databag**. In the "domain" section, select your chosen URL from the drop-down list. Under "type" select `HTTP`. Under "URL", enter your **Raspberry Pi's local IP address** followed by `:7000`. It should have the form: `XXX.XXX.XXX.XXX:7000`. Click `Save`. Then select your tunnel name to enter the next public hostname.

<img src="../Media_Repository/Cloudflare_Public_Hostname_databag.png" alt="Cloudflare Public Hostname Databag" title="Cloudflare Public Hostname Databag" width="40%"/> <img src="../Media_Repository/Cloudflare_Tunnel_Select.png" alt="Cloudflare Tunnel Select" title="Cloudflare Tunnel Select" width="50%"/> 

Note: Technically you can use any open port number for Databag, not just ":7000". However, ":7000" is selected to match the port we will designate for Nextcloud in a later step. Do not change this number unless you know what you're doing.

### __Pi-hole__

Once your system is set up, this URL will take you to the control panel for an adblocker which will reduce the number of ads for all devices on your internet.

In the "subdomain" section, enter **pihole**. In the "domain" section, select your chosen URL from the drop-down list. Under "type" select `HTTP`. Under "URL", enter your **Raspberry Pi's local IP address** followed by `:8080`. It should have the form: `XXX.XXX.XXX.XXX:8080`. Click `Save`. 

<img src="../Media_Repository/Cloudflare_Public_Hostname_pihole.png" alt="Cloudflare Public Hostname Pihole" title="Cloudflare Public Hostname Pihole" width="40%"/> <img src="../Media_Repository/Cloudflare_Tunnel_Select.png" alt="Cloudflare Tunnel Select" title="Cloudflare Tunnel Select" width="40%"/>

Note: Technically you can use any open port number for Pi-hole, not just ":8080". However, ":8080" is selected to match the port we will designate for Nextcloud in a later step. Do not change this number unless you know what you're doing.

# __Next Step__

Your Raspberry Pi is now connected to the worldwide web! Hallelujah!

Before moving on, try connecting to your Raspberry Pi homepage via the worldwide web! Type `home.exampleWebURL` into your web browser's address bar, where `exampleWebURL` corresponds to your chosen **Web URL**, including the ".com", ".org", etc suffix on the end. This should take you to your Raspberry Pi's homepage from anywhere in the world. 

Note: When you install new programs on your Pi, each one needs to be manually connected to the internet for you to be able to access it from anyone, rather than just your local internet. This includes connecting your Cloudflare tunnel to them, as above, and also connecting the program to the web, which we will cover in the next section.

Next you will install a [secure communications system and home cloud server using Nextcloud](../Instructions/Nextcloud_Setup.md).
