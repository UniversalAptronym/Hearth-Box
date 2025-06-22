# __CasaOS Setup__

If typing into the terminal window was intimidating, don't worry! We exactly have one more line to enter. Type the following line into terminal and press Enter. A lot of text will start scrolling. Wait for this to finish.

Note: Terminal windows often do not accept `ctrl+v` commands to paste content. If you want to paste the following command, you may have to right-click in the terminal window (on some systems this automatically pastes text) or right-click and select paste.

1. `curl -fsSL https://get.casaos.io | sudo bash`

<img src="../Media_Repository/PuTTY_casaos.png" alt="PuTTY CasaOS Install" title="PuTTY CasaOS Install" width="40%"/>

  - This commands installs [CasaOS](https://casaos.io/) from an online repository, and a lot of text will scroll by while it installs. CasaOS is an operating system which will let you operate your Pi through a graphics-based desktop like an ordinary computer, rather than through a terminal, and lets you make use of many programs written by open-source programmers. And speaking of open-source programmers, we have a [list of open-source programers whose work we'd like you to consider supporting](../donations_list.md). Their hard work makes all of this and so much more possible, and they rely on donations to keep the lights on. The whole world benefits from the labor of open source programmers and they deserve all the support we can give them. (The comic below is not a joke. It is stone-cold reality.)

<img src="https://imgs.xkcd.com/comics/dependency.png" alt="XKCD 2347: Dependency" title="XKCD 2347: Dependency" width="40%"/>

2. This is the end of your time with terminal! In the final lines of CasaOS's installation output, you should see `- http://XXX.XXX.XXX.XXX (eth0)`. The **XXX.XXX.XXX.XXX** should be the same as the **local IP address** you gave to your Pi and recorded in the previous section. (Remember that **XXX** represents 1-3 digits, and **(eth0)** may be **(wlan0)** if you opted for a non-ethernet connection.) 

<img src="../Media_Repository/CasaOS_Terminal_IP_Address.png" alt="CasaOS Local IP Address" title="CasaOS Local IP Address" width="40%"/> 

3. Open an internet browser, type `http://XXX.XXX.XXX.XXX` (your **Raspberry Pi's local IP address**) into the URL bar, and press Enter. This will bring you to a browser webpage where you can access CasaOS, which is now running on your Raspberry Pi! You now have a fully functional mini-computer you can access through your internet browser.
- Note: You can only access your Raspberry Pi using your **Pi's local IP address** from devices which are all connected to the same internet router. We will be making it so that you can access your Pi from anywhere in the world in later sections.

<img src="../Media_Repository/CasaOS_Browser_1.png" alt="CasaOS Browser Local IP Address in URL Bar" title="CasaOS Browser Local IP Address in URL Bar" width="50%"/> 

4. Create a CasaOS account using the **CasoOS username** and **CasaOS password** you decided on and recorded earlier. This username and password will be how you log into CasaOS from now on.

<img src="../Media_Repository/CasaOS_Browser_2.png" alt="CasaOS Browser Account Setup 1" title="CasaOS Browser Account Setup 1" width="40%"/> <img src="../Media_Repository/CasaOS_Browser_3.png" alt="CasaOS Browser Account Setup 2" title="CasaOS Browser Account Setup 2" width="40%"/> 

5. You should see a page which looks like the following, with some minor differences. (I have altered my background, removed the Time widget, removed the news and recommended app feeds, and changed the default search bar to Duckduckgo. Duckduckgo is a search system like Google, but unlike Google it doesn't spy on you to sell your search history to advertisers.) 

<img src="../Media_Repository/CasaOS_Layout.png" alt="CasaOS Layout" title="CasaOS Layout" width="50%"/> <img src="../Media_Repository/CasaOS_Layout_Explained.png" alt="CasaOS Layout Explained" title="CasaOS Layout Explained" width="50%"/>

6. Take some time to familiarize yourself with this space. There's not much here yet, but we're going to fill it up with stuff and it's worth being comfortable with before you move on. As an exercise, type something into the search bar and see what happens. Using the Settings button in the top left to change your background, as in the image below.

<img src="../Media_Repository/CasaOS_Layout_Settings.png" alt="CasaOS Layout Settings" title="CasaOS Layout Settings" width="50%"/>

7. Finally, you need to tell your Pi where to find the Big Bear App Store, so you can use their apps. ("Store" is a bit misleading. All of these applications are free, and depend on your [donations](../donations_list.md) to do the work they do.) First, click on the App icon. Next, click the dropdown menu which says `### apps`, where `###` is some number. This will open a menu. In this menu, click `More Apps`. This will open a bar to type text into.

<img src="../Media_Repository/CasaOS_Apps_1.png" alt="CasaOS Apps 1" title="CasaOS Apps 1" width="30%"/> <img src="../Media_Repository/CasaOS_Apps_2.png" alt="CasaOS Apps 2" title="CasaOS Apps 2" width="30%"/> <img src="../Media_Repository/CasaOS_Apps_3.png" alt="CasaOS Apps 3" title="CasaOS Apps 3" width="30%"/> 

8. Type `https://icewhale.bigbeartechworld.com/big-bear-casaos.zip` into this bar and press Enter. This will add additional Apps you can install, maintained by Big Bear and the Big Bear community. If you scroll down, you'll see a bunch of apps with "BigBearCasaOS" as their listed category. We will be using software from here later.

<img src="../Media_Repository/CasaOS_Apps_4.png" alt="CasaOS Apps 4" title="CasaOS Apps 4" width="40%"/> <img src="../Media_Repository/CasaOS_Apps_5.png" alt="CasaOS Apps 5" title="CasaOS Apps 5" width="40%"/>

Now on to the next step. We're going to use [Nginx, Cloudflared, and port fowarding to safely connect your Raspberry Pi to the worldwide web](../Instructions/Cloudflared_Nginx_Setup_(Web_Connection).md).
