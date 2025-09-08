# __Nextcloud Setup (This is the program used to talk to others and store files on the cloud)__

In this section you will install Nextloud. This well let you and others securely communicate to each other over the worldwide web through text, voice, and video chats. It will also act as a cloud storage device, allowing you and others to save files online and synchronize them through devices.

## __Installing Nextcloud__


1. If you do not already have it open, access your Raspberry Pi by entering `home.[exampleweburl]` into your web browser, where `exampleWebURL` corresponds to your chosen **Web URL**, including the ".com", ".org", etc suffix on the end. Open the `App Store` button. Navigate to the "Nextcloud" installer with the "BigBearCasaOS tag beneath it, either by scrolling down, or typing `nextcloud` into the search bar. Then click `Install`.

<img src="../Media_Repository/Nextcloud_Install_1.png" alt="Nextcloud installation 1" title="Nextcloud installation 1" width="40%"/> <img src="../Media_Repository/Nextcloud_Install_2.png" alt="Nextcloud installation 2" title="Nextcloud installation 2" width="40%"/> 

2. This should bring up the following installation window, which you can scroll to see the entirety of. If it does not, scroll over the "Nextcloud" App and click the three dots which appear, then click `Settings`. There will be four tabs at the top of the Settings screen: cron, db-nextcloud, nextcloud, and redis-nextcloud. You will need to add, change, or confirm information on three of those tabs: cron, db-nextcloud, and nextcloud.

<img src="../Media_Repository/Nextcloud_Alt_Settings.png" alt="Nextcloud installation alt settings access" title="Nextcloud alt settings access" width="60%"/>

3. If you are not already on it, click the `cron` tab in the "Settings" window. ([Cron](https://en.wikipedia.org/wiki/Cron#) is a program used for scheduling automated repetitive tasks on a Linux operating system, like the one installed on your Raspberry Pi.) The below doesn't have anything to do with Cron details though, it just happens to be the first settings tab, which is where CasaOS puts the "Web UI" settings for a program - which is used to tell your Raspberry Pi how to open an app when you click on it from the homepage. 
  - Under "Web UI", use the drop-down menu to make sure the URL prefix is `https://`. This ensures that when you click the Nextcloud icon from your homepage, it uses a secure connection.
  - Under "Web UI", enter `nextcloud.[exampleURL]` into the first box after the prefix, where `exampleURL` corresponds to your chosen **Web URL**, including the ".com", ".org", etc suffix on the end.
  - Under "Web UI", delete everything in the second box after the prefix. Once you have done so, it should read ":Ports", where that text is greyed out.
  - Under "Web UI", make sure the third box after the prefix contains only a `/` symbol.

4. Click the `db-nextcloud` tab in the "Settings" window. This tab controls backend settings for PostgresSQL, a database management program which helps Nextcloud. You need to change the following setting for security reasons, but you will never use them unless you are a very advanced user.
  - Under "Environment Variables", there are columns labeled "Key" and "Value". Next to the key labeled "POSTGRES_PASSWORD", change the text in the value box to be a random sequence of letters and numbers like this "fsaDfstTEW4573KNWEnfk" (DO NOT USE THIS SPECIFIC SEQUENCE). You don't need to write this down or be able to remember it, it just needs to be random and long so bad actors can't have a program guess it.

5. Click the `nextcloud` tab in the "Settings" window. This tab controls backend settings for the Nextcloud program itself.
  - Under "Environment Variables", there are columns labeled "Key" and "Value". Next to the key labeled "OVERWRITEPROTOCOL", change the value to `https`, if it isn't that already. This ensures your Nextcloud program only uses secure communication protocols for transferring information.
  - Under "Environment Variables", there are columns labeled "Key" and "Value". Next to the key labeled "PHP_MEMORY_LIMIT", change the value to "1024M". This increases the size limit of the 'chunks' Nextcloud uses to send large files, improving transfer speeds.
  - Under "Environment Variables", there are columns labeled "Key" and "Value". Next to the key labeled "PHP_UPLOAD_LIMIT", change the value to "1024M". This increases the size limit of the 'chunks' Nextcloud uses to send large files, improving transfer speeds.
  - Under "Environment Variables", there are columns labeled "Key" and "Value". Next to the key labeled "POSTGRES_PASSWORD", change the text in the value box to be the same random sequence of letters and numbers as in step 4 above.

6. Press `Save` to confirm these settings. Wait for Nextcloud to finish changing itself to include the new settings (there will be a message telling you when this is done).

7. Click the `Files` app on the homepage. Then click the following files in order: `AppData` > `big-bear-nextcloud` > `html` > `config`. Then click the file named `config.php`. This opens a file containing settings which control how Nextcloud functions, some of which you will need to change or add.~~~
