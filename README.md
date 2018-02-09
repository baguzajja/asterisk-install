# asterisk-install

1- tar zxvf asterisk
2- sudo -s
3- apt-get update
4- apt-get install build-essential wget libssl-dev libncurses5-dev libnewt-dev libxml2-dev linux-headers-$(uname -r) libsqlite3-dev uuid-dev libjansson-dev

5- ./configure

6- make menuconfig

7- make

8-make install 
9-make config

10-make samples

11-cd contrib/init.d/ 

12-cp rc.debian.asterisk /etc/init.d/asterisk

13-nano /etc/init.d/asterisk 

{change :

DAMON=/usr/sbin/asterisk
 
ASTVARRUNDIT=/var/run/asterisk 

ASTETCOIR=/etc/asterisk

}
14-useradd -d /var/lib/asterisk asterisk

15-chown -R  asterisk /var/spool/asterisk /var/lib/asterisk /var/run/asterisk 

16-cp etc_default_asterisk /etc/default/asterisk 

17-nano /etc/default/asterisk 

{delete # from

AST_USE
R
ASR_GROUP

}
18- nano /etc/asterisk/asterisk.conf
 
{delete ; from live_dangerously
}
19-asterisk -cvvvv
20-/etc/init.d/asterisk	start 
21-update-rc.d asterisk defaults
22-touch /var/log/asterisk//cdr-csv//Master.cv
23-chown asterisk  /var/log/asterisk//cdr-csv//Master.cv
