*I pledge my Honor that I have abided by the Stevens Honor System*

For this lab, I already had [Ubuntu 20.04.4 LTS (Jammy Jellyfish)](https://releases.ubuntu.com/22.04.4/ubuntu-22.04.4-desktop-amd64.iso) installed. Below is how I found out which version of Ubuntu I was running:

```
$ cat /etc/os-release
PRETTY_NAME="Ubuntu 22.04.3 LTS"
NAME="Ubuntu"
VERSION_ID="22.04"
VERSION="22.04.3 LTS (Jammy Jellyfish)"
VERSION_CODENAME=jammy
ID=ubuntu
ID_LIKE=debian
HOME_URL="https://www.ubuntu.com/"
SUPPORT_URL="https://help.ubuntu.com/"
BUG_REPORT_URL="https://bugs.launchpad.net/ubuntu/"
PRIVACY_POLICY_URL="https://www.ubuntu.com/legal/terms-and-policies/privacy-policy"
UBUNTU_CODENAME=jammy
```

Then I followed the commands:

```
$ sudo apt update
$ sudo apt install gtkwave
$ sudo apt install git make gnat zlib1g-dev
$ git clone https://github.com/ghdl/ghdl
$ cd ghdl
$ ./configure --prefix=/usr/local
$ make
$ sudo make install
$ cd ..
$ git clone https://github.com/kevinwlu/dsd.git
$ mkdir vhdl
$ cd vhdl
$ cp ~/dsd/ghdl/*vhdl .
```
