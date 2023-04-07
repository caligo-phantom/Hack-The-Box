# Meow

## Connect to Starting Point VPN before starting the machine
Downloaded the ovpn file and used the following command in the directory where the downloaded ovpn file resides.

```
sudo openvpn --config starting_point_siddh32.ovpn
```

## TARGET MACHINE IP ADDRESS

```
10.129.12.149
```

## What does the acronym VM stand for?

```
Virtual Machine
```

## What tool do we use to interact with the operating system in order to issue commands via the command line, such as the one to start our VPN connection? It's also known as a console or shell.

```
Terminal
```

## What service do we use to form our VPN connection into HTB labs?

```
openvpn
```

## What is the abbreviated name for a 'tunnel interface' in the output of your VPN boot-up sequence output?

Run the following command.

```
siddh@pop-os:~/Downloads$ ifconfig
eno1: flags=4099<UP,BROADCAST,MULTICAST>  mtu 1500
        ether 50:81:40:9c:21:5f  txqueuelen 1000  (Ethernet)
        RX packets 0  bytes 0 (0.0 B)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 0  bytes 0 (0.0 B)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0

lo: flags=73<UP,LOOPBACK,RUNNING>  mtu 65536
        inet 127.0.0.1  netmask 255.0.0.0
        inet6 ::1  prefixlen 128  scopeid 0x10<host>
        loop  txqueuelen 1000  (Local Loopback)
        RX packets 2280  bytes 489205 (489.2 KB)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 2280  bytes 489205 (489.2 KB)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0

tun0: flags=4305<UP,POINTOPOINT,RUNNING,NOARP,MULTICAST>  mtu 1500
        inet 10.10.14.50  netmask 255.255.254.0  destination 10.10.14.50
        inet6 dead:beef:2::1030  prefixlen 64  scopeid 0x0<global>
        inet6 fe80::9f2f:a315:865f:8872  prefixlen 64  scopeid 0x20<link>
        unspec 00-00-00-00-00-00-00-00-00-00-00-00-00-00-00-00  txqueuelen 500  (UNSPEC)
        RX packets 0  bytes 0 (0.0 B)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 156  bytes 15740 (15.7 KB)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0

wlo1: flags=4163<UP,BROADCAST,RUNNING,MULTICAST>  mtu 1500
        inet 10.90.0.230  netmask 255.255.254.0  broadcast 10.90.1.255
        inet6 fe80::48fb:29b6:2aa6:1493  prefixlen 64  scopeid 0x20<link>
        ether c8:94:02:47:3e:4b  txqueuelen 1000  (Ethernet)
        RX packets 772929  bytes 987529933 (987.5 MB)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 505347  bytes 66728357 (66.7 MB)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0
```

The answer is:

```
tun
```

## What tool do we use to test our connection to the target with an ICMP echo request?

```
ping
```

```
siddh@pop-os:~/Downloads$ ping 10.129.12.149
PING 10.129.12.149 (10.129.12.149) 56(84) bytes of data.
64 bytes from 10.129.12.149: icmp_seq=1 ttl=63 time=264 ms
64 bytes from 10.129.12.149: icmp_seq=2 ttl=63 time=264 ms
64 bytes from 10.129.12.149: icmp_seq=3 ttl=63 time=264 ms
64 bytes from 10.129.12.149: icmp_seq=4 ttl=63 time=263 ms
64 bytes from 10.129.12.149: icmp_seq=5 ttl=63 time=264 ms
64 bytes from 10.129.12.149: icmp_seq=6 ttl=63 time=264 ms
64 bytes from 10.129.12.149: icmp_seq=7 ttl=63 time=263 ms
64 bytes from 10.129.12.149: icmp_seq=8 ttl=63 time=271 ms
64 bytes from 10.129.12.149: icmp_seq=9 ttl=63 time=264 ms
64 bytes from 10.129.12.149: icmp_seq=10 ttl=63 time=264 ms
64 bytes from 10.129.12.149: icmp_seq=11 ttl=63 time=267 ms
```

## What is the name of the most common tool for finding open ports on a target?

```
siddh@pop-os:~/Downloads$ nmap -p- -sV 10.129.12.149
Starting Nmap 7.80 ( https://nmap.org ) at 2023-04-06 21:03 IST
```

```
nmap
```

## What service do we identify on port 23/tcp during our scans?

```
telnet
```

```
siddh@pop-os:~/Downloads$ telnet 10.129.12.149
Trying 10.129.12.149...
Connected to 10.129.12.149.
Escape character is '^]'.

  █  █         ▐▌     ▄█▄ █          ▄▄▄▄
  █▄▄█ ▀▀█ █▀▀ ▐▌▄▀    █  █▀█ █▀█    █▌▄█ ▄▀▀▄ ▀▄▀
  █  █ █▄█ █▄▄ ▐█▀▄    █  █ █ █▄▄    █▌▄█ ▀▄▄▀ █▀█


Meow login:
```

## What username is able to log into the target over telnet with a blank password?

```
root
```

```
Meow login: root
Welcome to Ubuntu 20.04.2 LTS (GNU/Linux 5.4.0-77-generic x86_64)

 * Documentation:  https://help.ubuntu.com
 * Management:     https://landscape.canonical.com
 * Support:        https://ubuntu.com/advantage

  System information as of Thu 06 Apr 2023 03:49:22 PM UTC

  System load:           0.0
  Usage of /:            41.7% of 7.75GB
  Memory usage:          4%
  Swap usage:            0%
  Processes:             138
  Users logged in:       0
  IPv4 address for eth0: 10.129.12.149
  IPv6 address for eth0: dead:beef::250:56ff:fe96:5a4a


75 updates can be applied immediately.
31 of these updates are standard security updates.
To see these additional updates run: apt list --upgradable


The list of available updates is more than a week old.
To check for new updates run: sudo apt update

Last login: Mon Sep  6 15:15:23 UTC 2021 from 10.10.14.18 on pts/0
root@Meow:~# whoami
root
root@Meow:~# ls
flag.txt  snap
root@Meow:~# cat flag.txt
b40abdfe23665f766f9c61ecba8a4c19
```

## Glossary
- nmap -p- -sV 10.129.12.149 

```
"nmap" is a tool that helps to scan for open ports and services running on a computer or network.

"-p-" means "scan all ports" which means that nmap will check all the available ports on the target machine.

"-sV" means "service version detection" which means nmap will try to determine the specific version of each service running on each open port.

"-v" means "verbose" which means that nmap will give you more detailed output about what it's doing.

"10.129.12.149" is the IP address of the target machine that nmap will scan.

So, in simpler terms, this command tells nmap to scan all the available ports on a computer with the IP address of 10.129.12.149 and determine the specific version of each service running on each open port, and provide detailed output about what it's doing.
```

- tun

```
"Tun" is a type of virtual network interface that allows for secure communication between two networks over the internet. It's like a tunnel that connects two networks so that they can communicate with each other in a private and encrypted way.

Just like how you need a tunnel to travel from one place to another underground or through a mountain, tun creates a secure path between two networks so that information can be safely transported. Think of it as a secret tunnel that keeps the information inside safe from prying eyes.
```

- ping

```
"Ping" is a command used to test whether your computer can connect to another computer or device on a network, such as the internet.

When you "ping" another computer, your computer sends a message called an "echo request" to that computer. The other computer then sends back a response message called an "echo reply" to confirm that it received the message. This way, you can test if the other computer is reachable and how long it takes for the message to travel back and forth.

It's like playing a game of catch with your friend. You throw a ball to your friend and they catch it, and then they throw it back to you. If the ball comes back, you know your friend is there and ready to play. If it doesn't come back, you might need to look for your friend or try again later.
```

- telnet

```
"Telnet" is a command-line tool that allows you to connect to and communicate with another computer or device over a network, such as the internet.

When you use telnet, you can access the command line interface of another computer remotely, as if you were sitting in front of it. This allows you to execute commands on that computer, transfer files, or troubleshoot problems.

It's like using a telephone to talk to a friend who lives far away. You dial their number, they answer the phone, and you can talk to each other even though you're not in the same place. With telnet, you can connect to another computer and communicate with it as if you were physically there.
```
