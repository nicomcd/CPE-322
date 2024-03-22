*I pledge my Honor that I have abided by the Stevens Honor System*

- Go to the IoT repository
- Study Lessons 1 and 2
- Open a terminal

The following code block contains the commands from the lab assignment and its respective output:

```
$ hostname
Soy-Firefly

$ env
SHELL=/bin/bash
WSL_DISTRO_NAME=Ubuntu
NAME=Soy-Firefly
PWD=/home/nicoxmcd
LOGNAME=nicoxmcd
MOTD_SHOWN=update-motd
HOME=/home/nicoxmcd
LANG=C.UTF-8
WSL_INTEROP=/run/WSL/14_interop
LS_COLORS=rs=0:di=01;34:ln=01;36:mh=00:pi=40;33:so=01;35:do=01;35:bd=40;33;01:cd=40;33;01:or=40;31;01:mi=00:su=37;41:sg=30;43:ca=30;41:tw=30;42:ow=34;42:st=37;44:ex=01;32:*.tar=01;31:*.tgz=01;31:*.arc=01;31:*.arj=01;31:*.taz=01;31:*.lha=01;31:*.lz4=01;31:*.lzh=01;31:*.lzma=01;31:*.tlz=01;31:*.txz=01;31:*.tzo=01;31:*.t7z=01;31:*.zip=01;31:*.z=01;31:*.dz=01;31:*.gz=01;31:*.lrz=01;31:*.lz=01;31:*.lzo=01;31:*.xz=01;31:*.zst=01;31:*.tzst=01;31:*.bz2=01;31:*.bz=01;31:*.tbz=01;31:*.tbz2=01;31:*.tz=01;31:*.deb=01;31:*.rpm=01;31:*.jar=01;31:*.war=01;31:*.ear=01;31:*.sar=01;31:*.rar=01;31:*.alz=01;31:*.ace=01;31:*.zoo=01;31:*.cpio=01;31:*.7z=01;31:*.rz=01;31:*.cab=01;31:*.wim=01;31:*.swm=01;31:*.dwm=01;31:*.esd=01;31:*.jpg=01;35:*.jpeg=01;35:*.mjpg=01;35:*.mjpeg=01;35:*.gif=01;35:*.bmp=01;35:*.pbm=01;35:*.pgm=01;35:*.ppm=01;35:*.tga=01;35:*.xbm=01;35:*.xpm=01;35:*.tif=01;35:*.tiff=01;35:*.png=01;35:*.svg=01;35:*.svgz=01;35:*.mng=01;35:*.pcx=01;35:*.mov=01;35:*.mpg=01;35:*.mpeg=01;35:*.m2v=01;35:*.mkv=01;35:*.webm=01;35:*.webp=01;35:*.ogm=01;35:*.mp4=01;35:*.m4v=01;35:*.mp4v=01;35:*.vob=01;35:*.qt=01;35:*.nuv=01;35:*.wmv=01;35:*.asf=01;35:*.rm=01;35:*.rmvb=01;35:*.flc=01;35:*.avi=01;35:*.fli=01;35:*.flv=01;35:*.gl=01;35:*.dl=01;35:*.xcf=01;35:*.xwd=01;35:*.yuv=01;35:*.cgm=01;35:*.emf=01;35:*.ogv=01;35:*.ogx=01;35:*.aac=00;36:*.au=00;36:*.flac=00;36:*.m4a=00;36:*.mid=00;36:*.midi=00;36:*.mka=00;36:*.mp3=00;36:*.mpc=00;36:*.ogg=00;36:*.ra=00;36:*.wav=00;36:*.oga=00;36:*.opus=00;36:*.spx=00;36:*.xspf=00;36:
LESSCLOSE=/usr/bin/lesspipe %s %s
TERM=xterm-256color
LESSOPEN=| /usr/bin/lesspipe %s
USER=nicoxmcd
DISPLAY=/usr/local
SHLVL=1
WSLENV=
XDG_DATA_DIRS=/usr/local/share:/usr/share:/var/lib/snapd/desktop
PATH=/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/games:/usr/local/games:/usr/lib/wsl/lib:/mnt/c/Program Files/Common Files/Oracle/Java/javapath:/mnt/c/Python39/Scripts/:/mnt/c/Python39/:/mnt/c/Program Files (x86)/Common Files/Intel/Shared Libraries/redist/intel64/compiler:/mnt/c/WINDOWS/system32:/mnt/c/WINDOWS:/mnt/c/WINDOWS/System32/Wbem:/mnt/c/WINDOWS/System32/WindowsPowerShell/v1.0/:/mnt/c/WINDOWS/System32/OpenSSH/:/mnt/c/Program Files/Microsoft SQL Server/Client SDK/ODBC/110/Tools/Binn/:/mnt/c/Program Files (x86)/Microsoft SQL Server/120/Tools/Binn/:/mnt/c/Program Files/Microsoft SQL Server/120/Tools/Binn/:/mnt/c/Program Files/Microsoft SQL Server/120/DTS/Binn/:/mnt/c/Program Files (x86)/Windows Kits/8.1/Windows Performance Toolkit/:/mnt/c/Program Files (x86)/IVI Foundation/VISA/WinNT/Bin/:/mnt/c/Program Files/IVI Foundation/VISA/Win64/Bin/:/mnt/c/Program Files (x86)/IVI Foundation/VISA/WinNT/Bin:/mnt/c/ProgramData/chocolatey/bin:/mnt/c/Program Files/MATLAB/R2023b/bin:/mnt/c/Program Files/dotnet/:/mnt/c/Program Files/Git/cmd:/mnt/c/msys64/mingw64/bin:/mnt/c/msys64/usr/bin:/mnt/c/Users/nicom/AppData/Local/Microsoft/WindowsApps:/mnt/c/Users/nicom/AppData/Local/Programs/Microsoft VS Code/bin:/mnt/c/Users/nicom/AppData/Local/GitHubDesktop/bin:/mnt/c/Users/nicom:/mnt/c/Users/nicom/.dotnet/tools:/snap/bin
HOSTTYPE=x86_64
OLDPWD=/home/nicoxmcd/vhdl
_=/usr/bin/env

$ ps
  PID TTY          TIME CMD
   15 pts/0    00:00:01 bash
 4216 pts/0    00:00:00 ps

$ pwd
/home/nicoxmcd

$ git clone https://github.com/kevinwlu/iot.git
Cloning into 'iot'...
remote: Enumerating objects: 22856, done.
remote: Counting objects: 100% (3905/3905), done.
remote: Compressing objects: 100% (1202/1202), done.
remote: Total 22856 (delta 2194), reused 3766 (delta 2113), pack-reused 18951
Receiving objects: 100% (22856/22856), 28.77 MiB | 12.21 MiB/s, done.
Resolving deltas: 100% (14893/14893), done.

$ cd iot

$ ls
README.md  economics  lesson1   lesson3  lesson6  lesson9   special_problems  tools
apps       health     lesson10  lesson4  lesson7  make      standards
cases      hype       lesson2   lesson5  lesson8  projects  systems

$ cd

$ df
Filesystem     1K-blocks      Used Available Use% Mounted on
/dev/sdb       263174212   1947628 247788428   1% /
none             4010516         4   4010512   1% /mnt/wsl
tools          498725688 276715532 222010156  56% /init
none             4010516         4   4010512   1% /run
none             4010516         0   4010516   0% /run/lock
none             4010516         0   4010516   0% /run/shm
none             4010516         0   4010516   0% /run/user
tmpfs            4010516         0   4010516   0% /sys/fs/cgroup
drivers        498725688 276715532 222010156  56% /usr/lib/wsl/drivers
lib            498725688 276715532 222010156  56% /usr/lib/wsl/lib
drvfs          498725688 276715532 222010156  56% /mnt/c

$ mkdir demo

$ cd demo
```


This is what happens when you create a file using `nano`:
![Creating a file using nano](https://github.com/nicomcd/Engineering-Design-VI/blob/main/Images/Lab2nano.png)


```
$ nano file
$ cat file
$ cp file file1
$ mv file file2
$ rm file2
```


This is the terminal result after the final `rm file2`:
![Terminal Screenshot](https://github.com/nicomcd/Engineering-Design-VI/blob/main/Images/Lab2file.png)


```
$ clear
$ man uname
```


This is what happens when you get the manual for the command `uname`:
![Manual for uname](https://github.com/nicomcd/Engineering-Design-VI/blob/main/Images/Lab2man.png)


```
$ uname -a
Linux Soy-Firefly 5.10.102.1-microsoft-standard-WSL2 #1 SMP Wed Mar 2 00:30:59 UTC 2022 x86_64 x86_64 x86_64 GNU/Linux
```


When attempting to do `ifconfig` I received an error, and I remedied the problem by installing `deb net-tools`:


```
$ sudo su -
$ apt-get install net-tools
$ exit
```


![ifconfig error and fix](https://github.com/nicomcd/Engineering-Design-VI/blob/main/Images/Lab2ipconfigmod.png)



```
$ ifconfig
eth0: flags=4163<UP,BROADCAST,RUNNING,MULTICAST>  mtu 1500
        inet 172.20.111.203  netmask 255.255.240.0  broadcast 172.20.111.255
        inet6 fe80::215:5dff:fe7b:8aa5  prefixlen 64  scopeid 0x20<link>
        ether 00:15:5d:7b:8a:a5  txqueuelen 1000  (Ethernet)
        RX packets 141980  bytes 363328672 (363.3 MB)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 9574  bytes 698771 (698.7 KB)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0

lo: flags=73<UP,LOOPBACK,RUNNING>  mtu 65536
        inet 127.0.0.1  netmask 255.0.0.0
        inet6 ::1  prefixlen 128  scopeid 0x10<host>
        loop  txqueuelen 1000  (Local Loopback)
        RX packets 12  bytes 600 (600.0 B)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 12  bytes 600 (600.0 B)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0

$ ping localhost
PING localhost (127.0.0.1) 56(84) bytes of data.
64 bytes from localhost (127.0.0.1): icmp_seq=1 ttl=64 time=0.896 ms
64 bytes from localhost (127.0.0.1): icmp_seq=2 ttl=64 time=0.060 ms
64 bytes from localhost (127.0.0.1): icmp_seq=3 ttl=64 time=0.143 ms
64 bytes from localhost (127.0.0.1): icmp_seq=4 ttl=64 time=0.141 ms
64 bytes from localhost (127.0.0.1): icmp_seq=5 ttl=64 time=0.070 ms
64 bytes from localhost (127.0.0.1): icmp_seq=6 ttl=64 time=0.070 ms
64 bytes from localhost (127.0.0.1): icmp_seq=7 ttl=64 time=0.061 ms
64 bytes from localhost (127.0.0.1): icmp_seq=8 ttl=64 time=0.071 ms
64 bytes from localhost (127.0.0.1): icmp_seq=9 ttl=64 time=0.057 ms
[...]
--- localhost ping statistics ---
45 packets transmitted, 45 received, 0% packet loss, time 45737ms
rtt min/avg/max/mdev = 0.043/0.086/0.896/0.123 ms

$ netstat
Active Internet connections (w/o servers)
Proto Recv-Q Send-Q Local Address           Foreign Address         State
Active UNIX domain sockets (w/o servers)
Proto RefCnt Flags       Type       State         I-Node   Path
```
