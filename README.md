<p align="center">
<img src="https://i.imgur.com/SOufsEW.png" alt="Yoink-BS">
</p>

*A Freeleech Torrent Grabber for BrokenStones*
---

Requires python2.7 + pip + `$ pip install requests HTMLParser`

Usage: `python yoink-bs.py [option]`

Options:

- `--add-all-torrents-to-db`: adds all existing freeleech torrents to the yoink-bs database without downloading the .torrent file. Use this option if you want to ignore all existing freeleech torrents and only yoink new ones.
- `--recreate-yoink-bs-rc`: deletes existing ~/.yoink-bs-rc and generates new file with default settings. Use this if migrating from another version of yoink-bs.py
- `--help` or `-h` or `-?`: shows help message

Yoink-BS settings are stored in ~/.yoink-bs-rc and this file will be auto-generated on initial run. Accepted parameters are:

- `user`: your BrokenStones username
- `pass`: your BrokenStones password
- `target`: your torrent client watch directory
- `max_age`: the maximum age of a torrent in days that yoink-bs will download. If left blank, yoink-bs will not check the age of the torrent.
- `max_storage_in_mb`: the maximum size in megabytes of your storage directory. If the size of your storage directory exceeds the specified size, yoink-bs will stop downloading new torrents. This runs on the assumption that your torrent client preallocated the space required for each torrent immediately after the .torrent folder is added to your watch directory. If left blank, yoink-bs will not check the size of your storage area. This is intended for seedboxes with limited storage quotas.
- `storage_dir`: Your torrent data directory. If left blank, defaults to your home directory.
- `track_by_index_number`: TRUE or FALSE. If true, will write all downloaded torrent IDs to ~/.yoink-bs.db and use this as the primary mechanism for checking if a given torrent has already been yoinked.

To create a cron job that executes this script every hour, simply:

`$ crontab -e`

and add:

`00 * * * * python /path/to/yoink-bs.py`

*Now work out that buffer! (without blowing your storage quota)*

**Eternal thanks and gratitude flies out to:  [tobbez![<3](http://i.imgur.com/kX2q6Bm.png)](https://what.cd/user.php?id=605)  [evanjd/notarebel![<3](http://i.imgur.com/kX2q6Bm.png)](https://what.cd/user.php?id=417)  [phracker![<3](http://i.imgur.com/kX2q6Bm.png)](https://what.cd/user.php?id=260077)  [feralhosting![<3](http://i.imgur.com/kX2q6Bm.png)](https://www.feralhosting.com)**
