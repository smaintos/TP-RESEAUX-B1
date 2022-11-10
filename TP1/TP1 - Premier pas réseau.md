### TP1/B1-Réseau-2023 ###


**1. Affichage d'informations sur la pile TCP/IP locale**

🌞 **Affichez les infos des cartes réseau de votre PC**

* **nom, adresse MAC et adresse IP de l'interface WiFi**

```
smaintos@MacBook-Air-de-smaintos ~ % ifconfig

en0: flags=8863<UP,BROADCAST,SMART,RUNNING,SIMPLEX,MULTICAST> mtu 1500
	options=6463<RXCSUM,TXCSUM,TSO4,TSO6,CHANNEL_IO,PARTIAL_CSUM,ZEROINVERT_CSUM>
	ether fc:e2:6c:0f:cb:24 
	inet6 fe80::4f2:b3bb:6a7c:8810%en0 prefixlen 64 secured scopeid 0xb 
	inet 10.33.17.17 netmask 0xfffffc00 broadcast 10.33.19.255
	nd6 options=201<PERFORMNUD,DAD>
	media: autoselect
	status: active
```

* **nom, adresse MAC et adresse IP de l'interface Ethernet**

`J'en ai pas.`


🌞 **Affichez votre gateway**

* **utilisez une commande pour connaître l'adresse IP de la passerelle (ou gateway) de votre carte WiFi**


```
smaintos@MacBook-Air-de-smaintos ~ % ifconfig

en0: flags=8863<UP,BROADCAST,SMART,RUNNING,SIMPLEX,MULTICAST> mtu 1500
options=6463<RXCSUM,TXCSUM,TSO4,TSO6,CHANNEL_IO,PARTIAL_CSUM,ZEROINVERT_CSUM>
ether fc:e2:6c:0f:cb:24
inet6 fe80::4f2:b3bb:6a7c:8810%en0 prefixlen 64 secured scopeid 0xb
inet 10.33.17.17 netmask 0xfffffc00 **broadcast 10.33.19.255**
nd6 options=201<PERFORMNUD,DAD>
media: autoselect
status: active

"broadcast 10.33.19.255"
```

🌞 **Déterminer la MAC de la passerelle**

* **à l'aide d'une commande, affichez votre table ARP, et déterminez ainsi l'adresse MAC de la passerelle**

```
 Affichage de la table ARP :

smaintos@MacBook-Air-de-smaintos ~ % arp -a
? (10.33.16.2) at 72:85:b9:a6:4e:d2 on en0 ifscope [ethernet]
? (10.33.16.12) at c6:20:1c:b0:d:47 on en0 ifscope [ethernet]
? (10.33.16.19) at 32:b4:ba:eb:5d:ba on en0 ifscope [ethernet]
? (10.33.16.22) at 90:78:b2:a9:e8:eb on en0 ifscope [ethernet]
? (10.33.16.24) at e2:1:44:e1:b4:f2 on en0 ifscope [ethernet]
? (10.33.16.32) at 6e:89:2d:e7:56:46 on en0 ifscope [ethernet]
? (10.33.16.35) at c6:4d:78:17:a1:f4 on en0 ifscope [ethernet]
? (10.33.16.38) at de:d5:f6:1c:b2:2 on en0 ifscope [ethernet]
? (10.33.16.52) at 8e:5d:2f:a5:51:a5 on en0 ifscope [ethernet]
? (10.33.16.56) at 66:ca:6e:11:9:ec on en0 ifscope [ethernet]
? (10.33.16.70) at 8e:e0:9c:9a:c2:78 on en0 ifscope [ethernet]
? (10.33.16.72) at a6:a4:44:9d:9f:41 on en0 ifscope [ethernet]
? (10.33.16.80) at 56:45:ce:85:4:20 on en0 ifscope [ethernet]
? (10.33.16.81) at 1a:ea:e:1d:3a:4f on en0 ifscope [ethernet]
? (10.33.16.83) at be:99:a5:f7:dc:ba on en0 ifscope [ethernet]
? (10.33.16.88) at 36:d3:e4:c6:2:b5 on en0 ifscope [ethernet]
? (10.33.16.92) at d6:8c:be:35:f6:e0 on en0 ifscope [ethernet]
? (10.33.16.109) at ba:2:c8:e9:bc:33 on en0 ifscope [ethernet]
? (10.33.16.118) at 8a:d8:b7:7f:27:b1 on en0 ifscope [ethernet]
? (10.33.16.130) at 4e:10:11:e7:50:72 on en0 ifscope [ethernet]
? (10.33.16.141) at 16:dd:d6:6e:80:9d on en0 ifscope [ethernet]
? (10.33.16.153) at e2:12:34:48:70:3b on en0 ifscope [ethernet]
? (10.33.16.174) at 8c:b8:7e:9a:b8:5c on en0 ifscope [ethernet]
? (10.33.16.181) at 9c:3e:53:8c:90:1b on en0 ifscope [ethernet]
? (10.33.16.194) at 1c:57:dc:5a:43:65 on en0 ifscope [ethernet]
? (10.33.16.213) at 58:6c:25:7f:a6:16 on en0 ifscope [ethernet]
? (10.33.17.14) at c6:f6:1:ca:58:9f on en0 ifscope [ethernet]
? (10.33.17.57) at 8:5b:d6:c6:22:76 on en0 ifscope [ethernet]
? (10.33.17.60) at 76:99:d3:30:8b:75 on en0 ifscope [ethernet]
? (10.33.17.61) at 90:cc:df:d9:3e:51 on en0 ifscope [ethernet]
? (10.33.17.62) at e2:af:c6:c4:ac:22 on en0 ifscope [ethernet]
? (10.33.17.64) at 56:95:59:5f:16:8f on en0 ifscope [ethernet]
? (10.33.17.65) at f8:4d:89:6a:5b:fd on en0 ifscope [ethernet]
? (10.33.18.225) at ba:d4:52:5:4b:42 on en0 ifscope [ethernet]
? (10.33.18.227) at f0:2f:4b:7:51:49 on en0 ifscope [ethernet]
? (10.33.18.228) at 5a:91:bb:34:e8:e3 on en0 ifscope [ethernet]
? (10.33.18.231) at 1e:ff:39:fc:7f:e6 on en0 ifscope [ethernet]
? (10.33.18.243) at 8c:85:90:b5:80:db on en0 ifscope [ethernet]
? (10.33.18.253) at a4:83:e7:6a:c1:ca on en0 ifscope [ethernet]
? (10.33.18.255) at c6:c:84:80:d3:48 on en0 ifscope [ethernet]
? (10.33.19.8) at 28:7f:cf:11:f1:39 on en0 ifscope [ethernet]
? (10.33.19.9) at f2:55:80:90:db:20 on en0 ifscope [ethernet]
? (10.33.19.21) at fa:80:54:45:a1:8 on en0 ifscope [ethernet]
? (10.33.19.33) at d0:c6:37:fb:e:a0 on en0 ifscope [ethernet]
? (10.33.19.34) at d2:5e:4d:a7:6e:96 on en0 ifscope [ethernet]
? (10.33.19.37) at 36:98:5:f5:ee:5a on en0 ifscope [ethernet]
? (10.33.19.135) at 4a:e8:8f:11:6:bf on en0 ifscope [ethernet]
? (10.33.19.137) at da:27:73:dd:fa:7c on en0 ifscope [ethernet]
? (10.33.19.151) at 3e:1a:c8:e8:73:c0 on en0 ifscope [ethernet]
? (10.33.19.184) at b2:cc:96:7d:eb:52 on en0 ifscope [ethernet]
? (10.33.19.254) at 0:c0:e7:e0:4:4e on en0 ifscope [ethernet]
? (10.33.19.255) at ff:ff:ff:ff:ff:ff on en0 ifscope [ethernet]
? (169.254.29.88) at 58:6c:25:7f:a6:16 on en0 [ethernet]
? (169.254.136.1) at 8c:b8:7e:9a:b8:5c on en0 [ethernet]
? (224.0.0.251) at 1:0:5e:0:0:fb on en0 ifscope permanent [ethernet]

Filtre de la ligne avec l'adresse MAC Passerelle

smaintos@MacBook-Air-de-smaintos ~ % arp -a | grep 10.33.19.254
? (10.33.19.254) at 0:c0:e7:e0:4:4e on en0 ifscope [ethernet]
```

🌞**Trouvez comment afficher les informations sur une carte IP (change selon l'OS)**

* **trouvez l'IP, la MAC et la gateway pour l'interface WiFi de votre PC**

 **Chemin :** "A propose de ce mac" , "Rapport Sytème" , "Réseau" , "Wifi"
![](https://i.imgur.com/SoRYUP9.png)

### 2. Modifications des informations ###

### A. Modification d'adresse IP (part 1) ###
🌞 **Utilisez l'interface graphique de votre OS pour changer d'adresse IP :**

**changez l'adresse IP de votre carte WiFi pour une autre
ne changez que le dernier octet**

* **par exemple pour 10.33.1.10, ne changez que le 10**

* **valeur entre 1 et 254 compris**


**Chemin :** "Préférence Système" , "Réseau" ,  Je sélectionne le réseau wifi d'Ynov , "Avancé" , "TCP/IP" , Puis je change manuellement l'adresse ip.

![](https://i.imgur.com/veYCxjm.jpg)

🌞 **Il est possible que vous perdiez l'accès internet. Que ce soit le cas ou non, expliquez pourquoi c'est possible de perdre son accès internet en faisant cette opération.**

Si on ce fait déconnecter d'internet après cette manipulation viens du fait que l'adre!
sse IP de base de votre connexion est donner par le serveur DHCP , en changeant cette adresse le serveur ne vous reconnez plus , il faut juste se reconnecter.

### II. Exploration locale en duo ###

**Modifiez l'IP des deux machines pour qu'elles soient dans le même réseau**

![](https://i.imgur.com/xzWs0Vq.png)

**Vérifier à l'aide d'une commande que votre IP a bien été changée :**

```
PS C:\Users\lucas>ipconfig /all
  
   
   Carte Ethernet Ethernet :

   Suffixe DNS propre à la connexion. . . :
   Description. . . . . . . . . . . . . . : Realtek Gaming GbE Family Controller
   Adresse physique . . . . . . . . . . . : C0-18-03-59-30-32
   DHCP activé. . . . . . . . . . . . . . : Non
   Configuration automatique activée. . . : Oui
   Adresse IPv6 de liaison locale. . . . .: fe80::e1c2:fd45:f4f0:e17d%18(préféré)
   Adresse IPv4. . . . . . . . . . . . . .: 10.10.10.251(préféré)
   Masque de sous-réseau. . . . . . . . . : 255.255.255.0
   Passerelle par défaut. . . . . . . . . :
   IAID DHCPv6 . . . . . . . . . . . : 163584003
   DUID de client DHCPv6. . . . . . . . : 00-01-00-01-29-6A-1A-C4-C0-18-03-59-30-32
   NetBIOS sur Tcpip. . . . . . . . . . . : Activé
```

**Vérifier que les deux machines se joignent**
```

PS C:\Users\titim> ping  10.10.10.250

Envoi d’une requête 'Ping'  10.10.10.250 avec 32 octets de données :
Réponse de 10.10.10.250 : octets=32 temps=1 ms TTL=128
Réponse de 10.10.10.250 : octets=32 temps=1 ms TTL=128
Réponse de 10.10.10.250 : octets=32 temps=1 ms TTL=128
Réponse de 10.10.10.250 : octets=32 temps=2 ms TTL=128

Statistiques Ping pour 10.10.10.250:
    Paquets : envoyés = 4, reçus = 4, perdus = 0 (perte 0%),
Durée approximative des boucles en millisecondes :
    Minimum = 1ms, Maximum = 2ms, Moyenne = 1ms
```
**Déterminer l'adresse MAC de votre correspondant**
```
arp -a
Interface : 10.10.10.251 --- 0x12
  Adresse Internet      Adresse physique      Type
  10.10.10.250          b0-25-aa-47-c7-a4     dynamique
  10.10.10.255          ff-ff-ff-ff-ff-ff     statique
  169.254.139.228       b0-25-aa-47-c7-a4     dynamique
  224.0.0.22            01-00-5e-00-00-16     statique
  224.0.0.251           01-00-5e-00-00-fb     statique
  224.0.0.252           01-00-5e-00-00-fc     statique
  239.255.255.250       01-00-5e-7f-ff-fa     statique
  255.255.255.255       ff-ff-ff-ff-ff-ff     statique!
```

**Utilisation d'un des deux comme gateway**

![](https://i.imgur.com/6GQBRta.png)

**Tester l'accès internet :**

```
PS C:\Users\titim> ping 1.1.1.1

Envoi d’une requête 'Ping'  1.1.1.1 avec 32 octets de données :
Réponse de 1.1.1.1 : octets=32 temps=20 ms TTL=55
Réponse de 1.1.1.1 : octets=32 temps=20 ms TTL=55
Réponse de 1.1.1.1 : octets=32 temps=21 ms TTL=55
Réponse de 1.1.1.1 : octets=32 temps=20 ms TTL=55

Statistiques Ping pour 1.1.1.1:
    Paquets : envoyés = 4, reçus = 4, perdus = 0 (perte 0%),
Durée approximative des boucles en millisecondes :
    Minimum = 20ms, Maximum
```
**Prouver que la connexion Internet passe bien par l'autre PC :**

```
 PS C:\Users\titim> tracert 192.168.137.2

Détermination de l’itinéraire vers DESKTOP-0JKFI2T [192.168.137.2]
avec un maximum de 30 sauts :

  1     2 ms     1 ms     1 ms  DESKTOP-0JKFI2T [192.168.137.2]
```

Itinéraire déterminé.

### Petit chat privé ###

**sur le PC serveur :**

```
PS C:\Users\lucas\netcat-1.11> .\nc.exe -l -p 8888
```

**sur le PC client:**

`PS C:\Users\lucas\Desktop\netcat-win32-1.11\netcat-1.11> .\nc.exe 192.168.137.1 8888`

**CONVERSATION :**

```
[fmaxance] : Salut !
[blucas] : Salut
```

**Visualiser la connexion en cours**
```

PS C:\Users\lucas> netstat -a -n -b

  TCP    192.168.137.1:8888     192.168.137.2:56320    ESTABLISHED
 [nc.exe]
```
 
**Pour aller un peu plus loin**

**IP non définie :**

```
PS C:\Users\lucas\netcat-1.11> ./nc.exe -l -p 8888

PS C:\Users\lucas> netstat -a -n -b | Select-String 8888

  TCP    0.0.0.0:8888           0.0.0.0:0              LISTENING
```
  
**N'importe qui peut se connecter sur le serveur car l'IP est non définie.**

**IP définie :**

```
PS C:\Users\lucas\netcat-1.11> ./nc.exe -l -p 8888 -s 192.168.137.1
PS C:\Users\lucas> netstat -a -n -b | Select-String 8888

  TCP    192.168.137.1:8888     0.0.0.0:0              LISTENING
```

### Firewall ###

**🌞 Activez et configurez votre firewall**


![](https://i.imgur.com/VH8Bylp.png)

### III. Manipulations d'autres outils/protocoles côté client ###

### 1. DHCP ###

**🌞Exploration du DHCP, depuis votre PC**

![](https://i.imgur.com/620KFEM.png)

### 2. DNS ###

**🌞Trouver l'adresse IP du serveur DNS que connaît votre ordinateur****

![](https://i.imgur.com/AH59uLK.png)

**🌞 Utiliser, en ligne de commande l'outil nslookup (Windows, MacOS) ou dig (GNU/Linux, MacOS) pour faire des requêtes DNS à la main**


faites un lookup (lookup = "dis moi à quelle IP se trouve tel nom de domaine")

pour google.com

pour ynov.com

interpréter les résultats de ces commandes

![](https://i.imgur.com/uRuqqia.png)

![](https://i.imgur.com/Umj5R0l.png)

Ynov gère différent son flux , google n'a qu'une seule IP tandis qu'Ynov en a plusieurs.



déterminer l'adresse IP du serveur à qui vous venez d'effectuer ces requêtes

faites un reverse lookup (= "dis moi si tu connais un nom de domaine pour telle IP"

![](https://i.imgur.com/olZzkfN.png)


![](https://i.imgur.com/rUaPyNc.png)

### IV. Wireshark ###

Pas de carte réseau , pas d'adaptateur.










