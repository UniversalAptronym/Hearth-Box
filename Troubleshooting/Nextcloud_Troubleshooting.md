The Nextcloud folder route for BigBearCasaOS is `Root/DATA/AppData/big-bear-nextcloud`. This should be substituted for all examples of "..." below unless you have a custom installation.

## __Problems with File Syncing__

### __Filename Issues__

Nextcloud sometimes has issues with files with a lot of periods (.) in the filename, which aren't immediately followed by a file extension (like .mp4 or .vlc or .exe). Don't store files with names like this. Actually just in general, even ignoring Nextcloud, don't do it. It can cause problems.

### __File Locking__

This one should be your first stop if Nextcloud rejects attempts to change files, like saving updates to a text file. Go to .../html/config and open config.php. SAVE A COPY OF THIS FILE AS A BACKUP BEFORE MODIFYING IT. Search for the line:

> 'filelocking.enabled' => false,

If this line is not present, inserting it at the end like this may solve your issues.

<img src="../Media_Repository/Nextcloud_Filelocking.png" alt="Nextcloud Filelocking" title="Nextcloud Filelocking" width="50%"/> 

This is not recommended for large professional servers as it can cause problems with large data transfers by multiple users. However for small scale private servers, frankly I find filelocking (which sets certain conditions for files not being moved or updated) causes far more problems than it solves.

### __Server replied "413 Request Entity Too Large"__

Could be three things. 

#### __CasaOS Nexcloud Setting__

Open Nextcloud's settings UI. Go to the third tab `nextcloud`. Change `PHP_MEMORY_LIMIT` and `PHP_UPLOAD_LIMIT` to a higher value. I use 50G.

#### __Nginx Proxy Manager Setting__

Go to `Root/DATA/AppData/config/nginx/site-confs/default.conf`.

Find the setting `client_max_body_size [...];`. `[...]` will likely be 512M. Change it to a higher value to allow larger file transfers. I use 50G.
Find the setting `client_body_timeout [...]s;`. Change `[...]` to 3600s to allow for long transfer times.
Find the setting `fastcgi_buffers [...] [...];`. Change `[...] [...]` to 64 4k to allow for a bigger buffer.

### __PHP Setting Override__

Not sure if this helped, but apparently you can also add this to `Root/DATA/AppData/config/php/php-local.ini`.

`; Edit this file to override php.ini directives`

`upload_max_filesize = 100G`

`post_max_size = 100G`

`max_execution_time = 3600`

`memory_limit = 512M`

#### __Delete Sync Files__

Turn Nextcloud off on your PC. Go to your Nextcloud folder. View hidden files. Delete all "sync" files (these have sync in the name and .db as file extensions) and `.nextcloudsync.log`. Turn Nextcloud back on. It may take some time to repopulate the sync files if you have a large number of files.

### __Problems After Restarting The Pi__

If you see this after restarting your Pi:
`Internal Server Error
The server encountered an internal error and was unable to complete your request.
Please contact the server administrator if this error reappears multiple times, please include the technical details below in your report.
More details can be found in the server log.`
Nextcloud may needed to be restarted manually.
