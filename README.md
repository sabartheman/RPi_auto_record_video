This python script needs to be put into a startup sequence like
1. init.d
2. rc.local
3. root crontab

To run on startup in the background.  It should run until the pi is turned off/shutdown.

Currently how this used by the creator is to do the series of steps

1. enter into the terminal: sudo crontab -e
2. at the very bottom of the file enter in:@reboot python /home/pi/bin/python/auto_record/repeat_10m.py
3. restart the pi


**this is assuming that you have the video recording starting right away on the pi, 

Example: (having this command running through a script or just typing it into the command line)

raspivid -w 1280 -h 720 -b 1500000 -pf baseline -fps 24 -t 0 -n -hf -vf -o - | cvlc stream:///dev/stdin --sout '#rtp{sdp=rtsp://:8554/}' :demux=h264
