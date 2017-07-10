This python script needs to be put into a startup sequence like
1. init.d
2. rc.local
3. root crontab

To run on startup in the background.  It should run until the pi is turned off/shutdown.

Currently how this used by the creator is to do the series of steps

1. enter into the terminal: sudo crontab -e
2. at the very bottom of the file enter in:@reboot python /home/pi/bin/python/auto_record/repeat_10m.py
3. restart the pi
