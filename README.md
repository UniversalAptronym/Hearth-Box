**==================================================**
# __About This Project__
**==================================================**

[Setup and Installation Guide](../../wiki/Setup-and-Installation)

Welcome to the Hearth Box project. Our primary goal is to provide an easy to use and affordable method for oppressed and at-risk groups (such as the LGBT+ community and religious or ethnic minorities) to communicate securely without fear of surveillance, censorship, or government violence. Our secondary goal is to make it easier for people to manage and store their own data online, without relying on expensive and intrusive tech monopolies. This guide will show you how to set up a secure, end-to-end encrypted, self-hosted communication server which includes text, voice, and video chat, and which can be modified to include encrypted, remotely-accessible cloud storage and ad blocking. 

This guide will show you how to set up a "Hearth Box". A Hearth Box is a device you physically own, which hosts a secure, end-to-end encrypted, self-hosted server accessible on the worldwide web. What this means is that you and others can communicate through it via text, voice, and video chat, on your personal computers and mobile devices, without censorship and without anyone intercepting and reading your communications en-route. A Hearth Box also enables cloud storage of your personal data, which likewise cannot be censored or spied on by third parties. Finally, as an extra perk, a Hearth Box can help filter some internet ads which standard ad-blockers may miss.

(left) An example of a Hearth Box. (right) An example of one of the communication platforms hosted on a Hearth Box

<img src="Media_Repository/Raspberry_Pi_5_and_SSD_enclosed.jpg" alt="Enclosed Pi 5 and SSD" title="Enclosed Pi 5 and SSD" width="40%"/> <img src="Media_Repository/Nextcloud_Talk_Example.png" alt="Nextcloud talk example" title="Nextcloud talk example" width="50%"/> 

Our primary goal is to provide an *easy to use* and affordable method for oppressed and at-risk groups (such as the LGBT+ community and religious or ethnic minorities) to communicate securely without fear of surveillance, censorship, or government violence. Our secondary goal is to make it easier for people to manage and store their own data online, without relying on expensive and intrusive tech monopolies. We have written these documents with ease of access in mind and they intended to be accessible even by those with little to no technical expertise. This guide will show you how to set up a "Hearth Box" secure, end-to-end encrypted, self-hosted server (i.e. information sent through this server en-route by anyone other than their intended recipients) using hardware you physically possess, which enables text, voice, and video chat, and also remotely-accessible cloud storage and ad blocking. 

The server on a Hearth Box facilitates communication which is much more difficult for governments or malicious actors to surveil than other methods like texting, Facebook Messenger, Instagram, WhatsApp, or Discord. While we suggest the [Signal app](https://signal.org/#signal) as an easier-to-use alternative for secure, end-to-end encrypted communication, it is blocked in some countries as of 2025, (such as [Russia, Venezuela,](https://www.theverge.com/2024/8/9/24217008/signal-blocked-venezuela-russia) [China, and Iran](https://www.techradar.com/news/china-blocks-signal-heres-what-you-need-to-know)). This can be circumvented by a virtual private network (VPN), but those services are often restricted by government censorship as well.

While no form of digital communication is definitively secure, encrypted self-hosted communication systems are far more difficult to usefully surveil, interfere with, or ban. Using self-hosted servers to communicate is infinitely more secure than communicating with programs like WhatsApp or Discord, which can read your messages and which regularly cooperate with governments' requests to access users' messages and other data. However, a self-hosted server will not protect you from [FBI spyware installed directly on your computer](https://www.nbcnews.com/id/wbna3341694), if that is used to gain access to your usernames and passwords. When discussing private information online, remember that the best security is always caution and nothing is foolproof.

So, should you build a Hearth Box? It depends. If you're a member of an at-risk group, this system could provide a substantial boost to your safety. If you live in the United States and you or someone you know is part of the LGBT+ community, you might consider building a server to insulate yourself from spying by the federal government, since the [Department of Homeland Security will surveil people based solely on their sexual orientation or gender identity](https://www.advocate.com/politics/dhs-allows-surveillance-sexual-orientation). If you pay monthly fees for cloud storage services such as Google Drive, iCloud, or Dropbox, or for encrypted telecommunication services such as Doxy.me or Zoom Business, building a home server may be cheaper for you in the long run. Finally, as an extra perk, a Hearth Box can help filter some internet ads which standard ad-blockers may miss.

If you are not part of an at-risk group and don't know anyone who is, you are not paying for cloud or communication services, and you don't care about ads, you may still want to consider self-hosting on privacy grounds. Most major communication programs are neither secure nor private, and often sell your data or give it to the police without a warrant. Most online file-storage programs (such as Google Drive, Microsoft OneDrive, and Adobe Creative Cloud storage) store your files unencrypted, and some even sell private information from them to advertisers or use the files you store on them to train AI models. If you, like us, consider this a gross invasion of privacy, then you should consider building a Hearth Box.

*Authors' note, 18 May 2025: This is a new project, and therefore a work in progress. Much of the content is missing from this guide. Please be patient while we fill it out.*

# __Instructions__

Follow these instructions step by step to make a secure communication hub / home server. Each step links to a detailed list of instructions.

We want to make this project accessible to _as many people as possible_, which means these instructions are written for people with little to no experience building computers, making websites, or self-hosting. Consequently, we've made individual steps in this guide as simple as possible. That also means that there are a lot of steps, but don't let the length of the guide intimidate you! (If you're an IT expert, you may find these instructions overly detailed; we hope they're still useful to you.) Whether you're a novice with computers and need your hand held through each step, or if you're an IT expert who happens to trip over some particular pain point, we don't want anyone to give up on making a home server because we didn't explain it carefully enough.

 1. Decide what you're getting.

    (_Authors' Note:_ If you're in the United States, the 2025 tariffs have substantially increased the prices for electronics. The prices listed in this guide may no longer be accurate, but the market is too volatile to keep them updated. For lower prices or improved availability, we suggest buying refurbished equipment if possible, with the exception of hard drives. If you choose to purchase refurbished hard drives as well, be aware they they can be unreliable and you should be especially vigilant about backing up any data stored on your Hearth Box.)

    1. [Full Home Server with Cloud Storage and Secure Communication](Equipment_List/Description_Full_Home_Server.md) (~$150-200 + $10/yr)
    2. [Secure Communication Only](Equipment_List/Description_Secure_Communication_Only.md) (~$50-70 + $10/yr) (under construction)
 2. Buy the equipment you need from [this list](Equipment_List/README.md).
 3. Get a domain name (web URL) and set it up. When you are finished, you and others will access your communication server by going to this URL. [Setting up a web URL with Cloudflare.md](Instructions/Cloudflare_(Web_URL).md)
 4. Install the imaging software. This software lets you use your computer to install other software onto your equipment.
    Authors' Note: (Beginner) is aspirational. For now we're only putting together the resources for (Advanced).
    1. (Beginner) There are prepared images (copies of everything needed to make your Pi a computer with software) and scripts (programs which will ask you for your inputs) which will let you set everything up painlessly. You will only need to type in things like your wifi name and password, your desired usernames and passwords, your domain name, etc.
    2. ([Advanced](Instructions/Raspberry_Pi_Image_Setup.md)) There is a list of tools and instructions with which you can install a fresh Raspberry Pi OS and add everything you need. Nothing in this section is automated.
5. [Assemble your Raspberry Pi](Instructions/Raspberry_Pi_Assembly.md).
6. [Image an operating system](Instructions/Raspberry_Pi_Image_Setup.md) onto your Micro SD Card (Secure Communication Only) or your SSD (Full Home Server). These are the storage devices which will hold all the operational software for your equipment.
7. [Install SSH software](Instructions/SSH_setup.md) (this lets your computer talk to your Raspberry Pi during the installation).
8. [Log into your Pi and complete the installation, using CasaOS](Instructions/CasaOS_Setup.md).
9. [Set up Nginx, Cloudflared (not to be confused with Cloudflare), and port-forwarding](Instructions/Cloudflared_Nginx_Setup_(Web_Connection).md), which lets you and others connect to Nextcloud / Databag remotely over the internet.
10. (For full home server users). Set up your Nextcloud server, for secure communications and cloud storage.
11. Optional: Set up your Databag server, for extra secure communications.
12. Optional: [Install an advertisement and tracker blocker](Instructions/Pi-hole_Installation.md)
13. Talk to your friends and say hi to others.

# __Usernames and Passwords__

Before you start, you should to decide on the usernames, passwords, and emails you will use to log in to certain programs. You will need these later, and they are very important for your security. You should also decide on the URL for your Hearth Box.

**Warning:** Make sure these are usernames and passwords you can remember and which do not rely on simple patterns. If you absolutely must write them down, store them in a secure *offline* location.

**Warning:** None of these usernames or passwords should be the same as other usernames or passwords you use.

You will need:

## __For regular use__
 **Warning:** This is publically visible. *It should not match any usernames, passwords, or emails below*.
 
- **Web URL** (this is the URL you and others will use to access your Pi's services) **(IMPORTANT: This is publically visible and SHOULD NOT MATCH ANY USERNAMES BELOW)**

- **CasaOS username** (this is the username you use to log into your Pi through a web browser)
- **CasaOS password** (this is the password you use to log into your Pi through a web browser)
- **Nextcloud username** (this is the username you use to log into your home server storage, and an alternative secure communication service)
- **Nextcloud password** (this is the password you use to log into your home server storage, and an alternative secure communication service)

### __Optional: For Databag, a secure communication app which is clunkier than Nextcloud but has better operational security__
- **Databag username** (this is your username for the secure communication app) (Important: Do not ever set your browser to autocomplete this username)
- **Databag password** (this is your password for the secure communication app) (Important: Do not ever set your browser to autocomplete this password)

## __For regular use - Full Home Server Only__

### __Usernames and passwords you'll need during installation or for changing your system later__
**IMPORTANT:** None of these passwords should be the same as the others! 
- **Raspberry Pi hostname** (`hostname`.local is the name your Pi goes by when your computer talks to it) 
- **Raspberry Pi username** (this is the username you use to log into your Pi through the terminal) (if you don't know what that is yet, don't worry)
- **Raspberry Pi password** (this is the password you use to log into your Pi through the terminal)
- **Cloudflare email** (this is the email you use for a free account with a service which lets you receive and manage your web URL)
- **Cloudflare password** (this is the password you use to receive and manage your web URL)
- **Nginx email** (this is the email you use for a free account with a service which lets you send your computer passwords without other people intercepting them)
- **Nginx password** (this is the password you use for a free account with a service which lets you send your computer passwords without other people intercepting them) 
- **Databag admin password** (this is your administrator password for the secure communication app) 

### __Recorded information__
You will also need to record the following information during this installation. 

#### __Offline Recorded Information__
You should record this information somewhere offline, where you won't lose it.
- Your Raspberry **Pi's local IP address**
- Your network **router's local IP address**
- Your network **router's global IP address**

#### __Temporarily Recorded Information__
This information will be temporarily stored on your computer, and should be deleted when this setup is finished.
To prepare you should make:
- A folder named `Cloudflare_Setup_Files`.
In this folder you should make
  - An empty text file named `Cloudflare_Tunnel`.
  - An empty text file named `Cloudlflare_SSL_Certificate`.
  - An empty text file named `Cloudlflare_SSL_Private_Key`.

If you do not know how to make new folders or text files, see these guides for doing so with [Windows](Instructions/New_Folder_File_Instructions_(Windows).md) and [Mac](Instructions/New_Folder_File_Instructions_(Mac).md).


# __Let's Get Started!__

Click [here](Equipment_List/README.md) to begin your self-hosting journey!
