## __Cloudflare\_(Web\_URL)__

### __Nginx__

Once your system is set up, this URL will take you to part of your device's security interface.

In the `subdomain` section, enter **nginx**. In the `domain` section, select your chosen URL from the drop-down list. Under `type` select **HTTP**. Under `URL`, enter your **global IP address** followed by **:81**. It should have the form: **XXX.XXX.XXX.XXX:81**. Click `Save`. Then select your tunnel name to enter the next public hostname.

<img src="../Media_Repository/Cloudflare_Public_Hostname_nginx.png" alt="Cloudflare Public Hostname nginx" title="Cloudflare Public Hostname nginx" width="40%"/> <img src="../Media_Repository/Cloudflare_Tunnel_Select.png" alt="Cloudflare Tunnel Select" title="Cloudflare Tunnel Select" width="40%"/> 

(The information below was based on a misunderstanding of Cloudflared)

## __Nginx Proxy Manager__

Nginx Proxy Mananager creates what is known as a "reverse proxy" for the server on your Hearth Box. This is a bit of software which stands between your server and the worldwide web. It handles the mathematics of encryption for your server, and makes it more difficult for hackers and eavesdroppers to access your server directly. ([Here is an explanation, if you are curious.](https://www.cloudflare.com/learning/cdn/glossary/reverse-proxy/))

6. If you do not already have it open, access your Raspberry Pi by entering its `local IP address` into your web browser. Open the `App Store` button. Navigate to the "Nginx Proxy Manager" installer either by scrolling down, or typing `nginx` into the search bar. Then click `Install`. 

<img src="../Media_Repository/Nginx_Install_1.png" alt="Nginx Proxy Manager installation 1" title="Nginx Proxy Manager installation 1" width="40%"/> <img src="../Media_Repository/Nginx_Install_2.png" alt="Nginx Proxy Manager installation 2" title="Nginx Proxy Manager installation 2" width="40%"/> 

7. This should bring up the following installation window, which you can scroll to see the entirety of. Most of the following should already be entered, but check each installation field to ensure they have the following values:
- Docker Image: `jc21/nginx-proxy-manager`
- Tag: `latest`
- Title: `Nginx Proxy Manager`
- Icon URL: `https://cdn.jsdelivr.net/gh/IceWhaleTech/CasaOS-AppStore@main/Apps/NginxProxyManager/icon.png`
- Web UI:
  - Left button: `https://` (IMPORTANT: Note the "s". Use `https`, not `http`. The "s" signifies a "secure" connection.)
  - Leftmost text field: `nginx.exampleweburl`, where you replace `examplewebURL` with your Hearth Box's **Web URL**. Note that this should include the suffix `.com`, `.org`, or whatever else you selected.
- Network: `bridge`
(Click the `+ Add` button to the right of "Port" to add additional Host | Container | Protocol values.)
(These Host | Container values are "port" addresses, appended to a URL as `examplewebURL:XXX`, and can technically be any matching pair so long as they do not overlap with the port values of another program or device. For simplicity, please use the port values listed for all programs unless you are an expert user.)
- Ports:
  - Host: `82`| Container: `82` | Protocol: `TCP`
  - Host: `443`| Container: `443` | Protocol: `TCP`
  - Host: `81`| Container: `81` | Protocol: `TCP`
(Click the `+ Add` button to the right of "Volumes" to add additional Host | Container values.)
(These Host | Container values are the folder locations within your Raspberry Pi where parts of this program will be stored. For simplicity, please use the values listed unless you are an expert user.)
- Volumes:
  - Host: `/DATA/AppData/nginxproxymanager/data` | Container: `/data`
  - Host: `/DATA/AppData/nginxproxymanager/etc/letsencrypt` | Container: `/etc/letsencrypt`
- CPU Shares: `High`
- Restart Policy: `unless-stopped`
- Container Name: `nginxproxymanager`

When you are finished, click 'Save'.

<img src="../Media_Repository/Nginx_Install_3.png" alt="Nginx Proxy Manager installation settings 1" title="Nginx Proxy Manager installation settings 1" width="40%"/> <img src="../Media_Repository/Nginx_Install_4.png" alt="Nginx Proxy Manager installation settings 2" title="Nginx Proxy Manager installation settings 2" width="36%"/> 

8. Next you need to open Nginx Proxy Manager. When you are finished with this section, you will be able to do so by clicking the `Nginx Proxy Manager`. However, the `Web UI` field is configured so that clicking on this icon opens the web URL `https://nginx.examplewebURL`, and you do not yet have web connectivity enabled. Your Hearth Box can still only be connected to via your **Raspberry Pi's local IP address**. Instead, open a new web browser page and type into the address bar `http://XXX.XXX.XXX.XXX:82`, where **XXX.XXX.XXX.XXX** is your **Raspberry Pi's local IP address**. Then press Enter.

Reminder: Using your **Raspberry Pi's local IP address** to access your Hearth Box will only work when you are connecting to the internet through the same local router as your Raspberry Pi.

9. You should see the Nginx login page. In the next step you will set up your own personal **Nginx email** and **Nginx password**, but right now you will use the Nginx default email and password to log in. These are `admin@example.com` and `changeme` respectively. Type these into the `Email address` and `Password` boxes, then press `Sign In`.

<img src="../Media_Repository/Nginx_Login.png" alt="Nginx Proxy Manager login" title="Nginx Proxy Manager login" width="40%"/> <img src="../Media_Repository/Nginx_Login_Changes_1.png" alt="Nginx Proxy Manager email 1" title="Nginx Proxy Manager email 1" width="40%"/>

10. Click the account icon in the top right. Then click `Edit Details`. Change the "Email" box to your desired **Nginx Email**. You can change the "Full Name" and "Nickname" if you want, but it's not necessary. When you're finished, click `Save`.

<img src="../Media_Repository/Nginx_Login_Changes_2.png" alt="Nginx Proxy Manager email 2" title="Nginx Proxy Manager email 2" width="40%"/> <img src="../Media_Repository/Nginx_Login_Changes_3.png" alt="Nginx Proxy Manager email 3" title="Nginx Proxy Manager email 3" width="40%"/> 

11. Click the account icon in the top right. Then click `Change Password`. If the "Current Password" is not automatically filled in, type in `changeme`. Type your desired **Nginx password** into the "New Password" and "Confirm Password" boxes. When you're finished, click `Save`.

<img src="../Media_Repository/Nginx_Login_Changes_4.png" alt="Nginx Proxy Manager password 1" title="Nginx Proxy Manager password 1" width="40%"/> <img src="../Media_Repository/Nginx_Login_Changes_5.png" alt="Nginx Proxy Manager password 2" title="Nginx Proxy Manager password 2" width="40%"/> 

### __Adding An SSL Certificate And Private Key To Nginx__

12. Next you need to give Nginx your **SSL Certificate**, so it can perform encryption (an explanation of [SSL certificates](https://www.cloudflare.com/learning/ssl/what-is-an-ssl-certificate/) and [encryption](https://en.wikipedia.org/wiki/Public-key_cryptography) if you are curious). Click the `SSL Certificate` tab. Click `Add SSL Certificate`.

<img src="../Media_Repository/Nginx_SSL_Certificate_1.png" alt="Nginx Proxy Manager SSL Certificate 1" title="Nginx Proxy Manager SSL Certificate 1" width="40%"/> <img src="../Media_Repository/Nginx_SSL_Certificate_2.png" alt="Nginx Proxy Manager SSL Certificate 2" title="Nginx Proxy Manager SSL Certificate 2" width="40%"/> 

13. Enter your **Web URL** into the "Name" text box. 

14. Click the `Browse` button attached to "Certificate Key". Before beginning, you should have created a text file named `Cloudflare_SSL_Private_Key.txt`. Navigate to this file and select it, then click `Open`.

15. Click the `Browse` button attached to "Certificate". Before beginning, you should have created a text file named `Cloudflare_SSL_Certificate.txt`. Navigate to this file and select it, then click `Open`. Then click `Save`.

<img src="../Media_Repository/Nginx_SSL_Certificate_3.png" alt="Nginx Proxy Manager SSL Certificate 3" title="Nginx Proxy Manager SSL Certificate 3" width="40%"/> 

### __Adding A New Program To Nginx__

Pay careful attention to this section. You will need to repeat step 16-20 with a slight modification to `examplewebURL` each time you want to connect a program on your Hearth Box to the worldwide web.

First, we will connect your CasaOS dashboard to the web.

16. Click `Dashboard`, and then click `Proxy Hosts`. Click `Add Proxy Hosts.`

<img src="../Media_Repository/Nginx_Proxy_Host_1.png" alt="Nginx Proxy Manager proxy host 1" title="Nginx Proxy Manager proxy host 1" width="40%"/> <img src="../Media_Repository/Nginx_Proxy_Host_2.png" alt="Nginx Proxy Manager proxy host 2" title="Nginx Proxy Manager proxy host 2" width="40%"/> 

17. Under "Domain Names" enter `examplewebURL` where you replace `examplewebURL` with your Hearth Box's **Web URL**. Note that `examplewebURL` should include the suffix `.com`, `.org`, or whatever else you selected earlier.

18. Set the "Scheme" to `https`, where the "s" signifies a "secure" connection. In the "Forward Hostname / IP" text box, enter your **Raspberry Pi's local IP address**. In the "Forward Port" text box, enter `443`. (This is the "port" used to talk to websites preprended with "https".)

19. Click the following buttons to turn their options on: `Cache Assets`, `Block Common Exploits`, `Websockets Support`. Then click the `SSL` tab.

<img src="../Media_Repository/Nginx_Proxy_Host_Details.png" alt="Nginx Proxy Manager proxy host details" title="Nginx Proxy Manager proxy host details" width="50%"/>

20. Click inside the "SSL Certificate" box. From the drop down menu, click on the certificate with the name you entered in step 8. This should be your **Web URL**. Click the `Force SSL` and `HTTP/2 Support` options to turn them on. Then click `Save`.

<img src="../Media_Repository/Nginx_Proxy_Host_SSL_1.png" alt="Nginx Proxy Manager proxy host SSL 1" title="Nginx Proxy Manager proxy host SSL 1" width="40%"/> <img src="../Media_Repository/Nginx_Proxy_Host_SSL_2.png" alt="Nginx Proxy Manager proxy host SSL 2" title="Nginx Proxy Manager proxy host SSL 2" width="40%"/>

----------------------------

SCRATCH THIS

STILL NEED TO DO PORT FOWARDING APPARENTLY

This makes it so that your Raspberry Pi can securely accept requests to see your Hearth Box's **Web URL**! If you type `examplewebURL` into a web browser, where `examplewebURL` is your **Web URL**, it should take you to your CasaOS dashboard!

21. However, to access specific programs from the web, you will have to configure their own web URLs, with the appropriate prefixes. To configure "Nginx Proxy Manager", repeat steps 16-20, but replace `examplewebURL` with `nginx.examplewebURL`.

This (almost) makes it so that when you click the "Nginx Proxy Manager" icon on your CasaOS dashboard, or type `nginx.examplewebURL` (where `examplewebURL` is your **Web URL**) into a web browser, it will take you to Nginx!

There's just one more thing to do to connect : Port Forwarding.


