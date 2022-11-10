### TP1/B1-Réseau-2023 ###

### Setup IP ###

**🌞 Mettez en place une configuration réseau fonctionnelle entre les deux machines**

IP1 : 172.16.86.1/24
IP2 : 172.16.86.2/24
BROADCAST : 172.16.86.255

**🌞 Prouvez que la connexion est fonctionnelle entre les deux machines**

```
smaintos@MacBook-Air-de-smaintos ~ % ping 172.16.86.2
PING 172.16.86.2 (172.16.86.2): 56 data bytes
64 bytes from 172.16.86.2: icmp_seq=0 ttl=64 time=0.401 ms
64 bytes from 172.16.86.2: icmp_seq=1 ttl=64 time=0.550 ms
64 bytes from 172.16.86.2: icmp_seq=2 ttl=64 time=0.553 ms
64 bytes from 172.16.86.2: icmp_seq=3 ttl=64 time=0.638 ms
64 bytes from 172.16.86.2: icmp_seq=4 ttl=64 time=0.572 ms
^C
--- 172.16.86.2 ping statistics ---
5 packets transmitted, 5 packets received, 0.0% packet loss
round-trip min/avg/max/stddev = 0.401/0.543/0.638/0.078 ms
```
**🌞 Wireshark it**

**déterminez, grâce à Wireshark, quel type de paquet ICMP est envoyé par ping**

(voir le ptit pcap frer)

Le type de paquet envoyer par ping est "Echo request" et "Echo reply".

### II. ARP my bro ###

**🌞 Check the ARP table**

**utilisez une commande pour afficher votre table ARP**
```
william@william-virtual-machine:~$ ip n s
172.16.86.1 dev ens160 lladdr fe:e2:6c:f0:98:64 REACHABLE
```
**déterminez la MAC de votre binome depuis votre table ARP**

```
smaintos@MacBook-Air-de-smaintos ~ % arp -a
? (172.16.86.2) at 0:c:29:8c:f4:f2 on bridge100 ifscope [bridge]
```

**déterminez la MAC de la gateway de votre réseau**

```
smaintos@MacBook-Air-de-smaintos ~ % arp -a
? (10.33.19.254) at 0:c0:e7:e0:4:4e on en0 ifscope [ethernet]
```
**🌞 Manipuler la table ARP**


* **utilisez une commande pour vider votre table ARP**
* **prouvez que ça fonctionne en l'affichant et en constatant les changements**
* **ré-effectuez des pings, et constatez la ré-apparition des données dans la table ARP**


```
smaintos@MacBook-Air-de-smaintos ~ % arp -a
? (10.33.16.9) at da:b1:e:9e:f:69 on en0 ifscope [ethernet]
? (10.33.16.13) at e2:12:34:48:70:3b on en0 ifscope [ethernet]
? (10.33.16.24) at ba:2:c8:e9:bc:33 on en0 ifscope [ethernet]
? (10.33.16.27) at d6:8c:be:35:f6:e0 on en0 ifscope [ethernet]
? (10.33.16.29) at bc:7f:a4:33:dd:9b on en0 ifscope [ethernet]
? (10.33.16.32) at 4a:e8:8f:11:6:bf on en0 ifscope [ethernet]
? (10.33.16.33) at 16:dd:d6:6e:80:9d on en0 ifscope [ethernet]
? (10.33.16.35) at de:d5:f6:1c:b2:2 on en0 ifscope [ethernet]
? (10.33.16.40) at c6:4d:78:17:a1:f4 on en0 ifscope [ethernet]
? (10.33.16.42) at 8e:5d:2f:a5:51:a5 on en0 ifscope [ethernet]
? (10.33.16.48) at 32:b4:ba:eb:5d:ba on en0 ifscope [ethernet]
? (10.33.16.55) at d0:3c:1f:fd:6f:88 on en0 ifscope [ethernet]
? (10.33.16.56) at 66:ca:6e:11:9:ec on en0 ifscope [ethernet]
? (10.33.16.57) at da:27:73:dd:fa:7c on en0 ifscope [ethernet]
? (10.33.16.59) at b6:a1:cc:ac:a6:3b on en0 ifscope [ethernet]
? (10.33.16.60) at b6:7a:c6:63:23:79 on en0 ifscope [ethernet]
? (10.33.16.65) at 36:d3:e4:c6:2:b5 on en0 ifscope [ethernet]
? (10.33.16.68) at c8:89:f3:ac:3b:d4 on en0 ifscope [ethernet]
```

```
10.33.16.9 (10.33.16.9) deleted
10.33.16.13 (10.33.16.13) deleted
10.33.16.22 (10.33.16.22) deleted
10.33.16.24 (10.33.16.24) deleted
10.33.16.27 (10.33.16.27) deleted
10.33.16.29 (10.33.16.29) deleted
10.33.16.32 (10.33.16.32) deleted
10.33.16.33 (10.33.16.33) deleted
10.33.16.35 (10.33.16.35) deleted
10.33.16.40 (10.33.16.40) deleted
10.33.16.42 (10.33.16.42) deleted
10.33.16.48 (10.33.16.48) deleted
10.33.16.55 (10.33.16.55) deleted
10.33.16.56 (10.33.16.56) deleted
10.33.16.57 (10.33.16.57) deleted
10.33.16.59 (10.33.16.59) deleted
10.33.16.60 (10.33.16.60) deleted
10.33.16.65 (10.33.16.65) deleted
10.33.16.68 (10.33.16.68) deleted
10.33.16.69 (10.33.16.69) deleted
10.33.16.72 (10.33.16.72) deleted
10.33.16.73 (10.33.16.73) deleted
10.33.16.76 (10.33.16.76) deleted
10.33.16.79 (10.33.16.79) deleted
10.33.16.80 (10.33.16.80) deleted
10.33.16.81 (10.33.16.81) deleted
10.33.16.82 (10.33.16.82) deleted
10.33.16.83 (10.33.16.83) deleted
10.33.16.85 (10.33.16.85) deleted
```
------------------
```
smaintos@MacBook-Air-de-smaintos ~ % ping 172.16.86.2                
PING 172.16.86.2 (172.16.86.2): 56 data bytes
64 bytes from 172.16.86.2: icmp_seq=0 ttl=64 time=0.715 ms
64 bytes from 172.16.86.2: icmp_seq=1 ttl=64 time=0.503 ms
64 bytes from 172.16.86.2: icmp_seq=2 ttl=64 time=0.452 ms
64 bytes from 172.16.86.2: icmp_seq=3 ttl=64 time=0.559 ms
64 bytes from 172.16.86.2: icmp_seq=4 ttl=64 time=0.690 ms
64 bytes from 172.16.86.2: icmp_seq=5 ttl=64 time=0.597 ms
64 bytes from 172.16.86.2: icmp_seq=6 ttl=64 time=0.421 ms
64 bytes from 172.16.86.2: icmp_seq=7 ttl=64 time=0.603 ms
64 bytes from 172.16.86.2: icmp_seq=8 ttl=64 time=0.645 ms
64 bytes from 172.16.86.2: icmp_seq=9 ttl=64 time=0.569 ms
©64 bytes from 172.16.86.2: icmp_seq=10 ttl=64 time=0.678 ms
64 bytes from 172.16.86.2: icmp_seq=11 ttl=64 time=0.601 ms
64 bytes from 172.16.86.2: icmp_seq=12 ttl=64 time=0.580 ms
```

```
smaintos@MacBook-Air-de-smaintos ~ % arp -a
? (10.33.16.42) at 8e:5d:2f:a5:51:a5 on en0 ifscope [ethernet]
? (10.33.16.56) at 66:ca:6e:11:9:ec on en0 ifscope [ethernet]
? (10.33.16.57) at da:27:73:dd:fa:7c on en0 ifscope [ethernet]
? (10.33.16.72) at a6:a4:44:9d:9f:41 on en0 ifscope [ethernet]
? (10.33.16.76) at 1e:b5:8f:bf:60:8d on en0 ifscope [ethernet]
? (10.33.16.81) at 1a:ea:e:1d:3a:4f on en0 ifscope [ethernet]
? (10.33.16.85) at 9c:3e:53:75:38:b0 on en0 ifscope [ethernet]
? (10.33.16.107) at 94:e7: b:5:5a:fa on en0 ifscope [ethernet]
? (10.33.16.137) at 72:63:90:4d:2f:3b on en0 ifscope [ethernet]
? (10.33.16.254) at 1c:57:dc:5a:43:65 on en0 ifscope [ethernet]
? (10.33.17.7) at 8a:d8:b7:7f:27:b1 on en0 ifscope [ethernet]
? (10.33.17.20) at a4:42:3b:28:41:eb on en0 ifscope [ethernet]
? (10.33.17.24) at fc:e2:6c:f:cb:24 on en0 ifscope permanent [ethernet]
? (10.33.17.252) at 8:6d:41:c8:96:cc on en0 ifscope [ethernet]
? (10.33.18.11) at d4:57:63:e0:d8:28 on en0 ifscope [ethernet]
? (10.33.18.25) at a4:83:e7:7e:1b:b5 on en0 ifscope [ethernet]
? (10.33.18.28) at 9a:7d:f:57:55:77 on en0 ifscope [ethernet]
? (10.33.18.35) at 9a:47:14:7c:8d:cf on en0 ifscope [ethernet]
? (10.33.18.36) at ac:bc:32:bc:43:2f on en0 ifscope [ethernet]
? (10.33.18.37) at a:7:1e:9c:c0:83 on en0 ifscope [ethernet]
? (10.33.18.38) at bc:d0:74:41:6a:f6 on en0 ifscope [ethernet]
? (10.33.18.39) at e:32:ec:7b:8b:87 on en0 ifscope [ethernet]
? (10.33.18.44) at 3c:6:30:2b:2e:f on en0 ifscope [ethernet]
? (10.33.18.45) at f2:6b:2:7b:87:c3 on en0 ifscope [ethernet]
? (10.33.18.64) at 3c:6:30:0:20:2e on en0 ifscope [ethernet]
? (10.33.18.75) at 30:35:ad:d1:3c:30 on en0 ifscope [ethernet]
? (10.33.18.116) at ac:d5:64:94:34:53 on en0 ifscope [ethernet]
? (10.33.18.119) at a4:cf:99:4f:37:ea on en0 ifscope [ethernet]
? (10.33.18.187) at 2:61:67:dc:76:81 on en0 ifscope [ethernet]
? (10.33.19.151) at 3e:1a:c8:e8:73:c0 on en0 ifscope [ethernet]
? (10.33.19.254) at 0:c0:e7:e0:4:4e on en0 ifscope [ethernet]
? (10.33.19.255) at ff:ff:ff:ff:ff:ff on en0 ifscope [ethernet]
? (172.16.40.255) at ff:ff:ff:ff:ff:ff on bridge101 ifscope [bridge]
? (172.16.86.2) at 0:c:29:8c:f4:f2 on bridge100 ifscope [bridge]
? (172.16.86.255) at ff:ff:ff:ff:ff:ff on bridge100 ifscope [bridge]
```
-------------------------------

**🌞 Wireshark it**

    Destination: Broadcast (ff:ff:ff:ff:ff:ff)
    Source: fe:e2:6c:f0:98:64 
    
`Destination : VMware_8c:f4:f2	Source : e:e2:6c:f0:98:64	`

(voir pcap frer ARP)


### III. DHCP you too my brooo ###

**identifiez les 4 trames DHCP lors d'un échange DHCP**
**mettez en évidence les adresses source et destination de chaque trame**
**identifiez dans ces 4 trames les informations 1, 2 et 3 dont on a parlé juste au dessus**

IP : 10.33.17.24
IP PASSERELLE : 10.33.19.254
DNS : 8.8.8.8



