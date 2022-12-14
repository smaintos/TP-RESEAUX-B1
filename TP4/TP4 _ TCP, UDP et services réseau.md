# TP4 : TCP, UDP et services réseau

### I. First steps ###

**🌞 Déterminez, pour ces 5 applications, si c'est du TCP ou de l'UDP**

**🌞 Demandez l'avis à votre OS**

netstat

Discord.exe
```

sudo lsof -P -a -i4 -i6 -itcp

Discord   1811 smaintos   23u  IPv4 0x3ab0a036b898087f      0t0  TCP 10.33.17.24:49241->162.159.135.232:443 (ESTABLISHED)
Discord   1811 smaintos   25u  IPv4 0x3ab0a036b8975e9f      0t0  TCP 10.33.17.24:49243->162.159.135.232:443 (ESTABLISHED)
Discord   1811 smaintos   26u  IPv4 0x3ab0a036b897112f      0t0  TCP 10.33.17.24:49244->162.159.129.233:443 (ESTABLISHED)
Discord   1811 smaintos   27u  IPv4 0x3ab0a036b896a9af      0t0  TCP 10.33.17.24:49246->162.159.130.235:443 (ESTABLISHED)
Discord   1811 smaintos   29u  IPv4 0x3ab0a036b8971c3f      0t0  TCP 10.33.17.24:49242->162.159.133.234:443 (ESTABLISHED)
Discord   1811 smaintos   31u  IPv4 0x3ab0a036b8981e9f      0t0  TCP 10.33.17.24:49247->162.159.138.234:443 (ESTABLISHED)
Discord   1811 smaintos   35u  IPv4 0x3ab0a036b897dc3f      0t0  TCP 10.33.17.24:49245->par10s39-in-f22.1e100.net:443 (ESTABLISHED)
Discord   1834 smaintos   51u  IPv4 0x3ab0a036b896b4bf      0t0  TCP localhost:6463 (LISTEN)

voir discord protocol pcap
```

Chrome.exe

```
sudo lsof -P -a -i4 -i6 -itcp

Google    2257 smaintos   22u  IPv4 0x3ab0a036b896938f      0t0  TCP 10.33.17.24:49321->par21s19-in-f10.1e100.net:443 (ESTABLISHED)
Google    2257 smaintos   23u  IPv4 0x3ab0a036b897325f      0t0  TCP 10.33.17.24:49322->server-13-225-239-41.bru50.r.cloudfront.net:443 (ESTABLISHED)
Google    2257 smaintos   24u  IPv4 0x3ab0a036b897274f      0t0  TCP 10.33.17.24:49320->fra15s10-in-f78.1e100.net:443 (ESTABLISHED)
Google    2257 smaintos   26u  IPv4 0x3ab0a036b89774bf      0t0  TCP 10.33.17.24:49345->ec2-52-17-239-19.eu-west-1.compute.amazonaws.com:443 (ESTABLISHED)
Google    2257 smaintos   27u  IPv4 0x3ab0a036b895d38f      0t0  TCP 10.33.17.24:49323->server-13-225-239-77.bru50.r.cloudfront.net:443 (ESTABLISHED)
Google    2257 smaintos   28u  IPv4 0x3ab0a036b895912f      0t0  TCP 10.33.17.24:49324->server-13-225-239-41.bru50.r.cloudfront.net:443 (ESTABLISHED)
Google    2257 smaintos   30u  IPv4 0x3ab0a036b896b4bf      0t0  TCP 10.33.17.24:49285->172.67.72.22:443 (ESTABLISHED)
Google    2257 smaintos   31u  IPv4 0x3ab0a036b897538f      0t0  TCP 10.33.17.24:49317->par21s20-in-f14.1e100.net:443 (ESTABLISHED)
Google    2257 smaintos   32u  IPv4 0x3ab0a036b897dc3f      0t0  TCP 10.33.17.24:49288->ec2-3-224-171-138.compute-1.amazonaws.com:443 (ESTABLISHED)
Google    2257 smaintos   33u  IPv4 0x3ab0a036b896674f      0t0  TCP 10.33.17.24:49325->server-13-225-239-64.bru50.r.cloudfront.net:443 (ESTABLISHED)
Google    2257 smaintos   34u  IPv4 0x3ab0a036b8967d6f      0t0  TCP 10.33.17.24:49326->104.16.148.64:443 (ESTABLISHED)
Google    2257 smaintos   36u  IPv4 0x3ab0a036b896bfcf      0t0  TCP 10.33.17.24:49333->104.16.148.64:443 (ESTABLISHED)
Google    2257 smaintos   37u  IPv4 0x3ab0a036b896512f      0t0  TCP 10.33.17.24:49334->104.18.41.98:443 (ESTABLISHED)
Google    2257 smaintos   39u  IPv4 0x3ab0a036b8977fcf      0t0  TCP 10.33.17.24:49327->server-13-225-239-77.bru50.r.cloudfront.net:443 (ESTABLISHED)
Google    2257 smaintos   41u  IPv4 0x3ab0a036b8965c3f      0t0  TCP 10.33.17.24:49335->server-18-155-120-63.cdg52.r.cloudfront.net:443 (ESTABLISHED)

voir google protocol pcap
```

 Mail (application apple)
 
```
 sudo lsof -P -a -i4 -i6 -itcp
 
 Mail      2414 smaintos   29u  IPv4 0x3ab0a036b898b4bf      0t0  TCP 10.33.17.24:49380->wr-in-f108.1e100.net:993 (ESTABLISHED)
Mail      2414 smaintos   30u  IPv4 0x3ab0a036b8983fcf      0t0  TCP 10.33.17.24:49381->wr-in-f108.1e100.net:993 (ESTABLISHED)
Mail      2414 smaintos   32u  IPv4 0x3ab0a036b8983fcf      0t0  TCP 10.33.17.24:49381->wr-in-f108.1e100.net:993 (ESTABLISHED)
Mail      2414 smaintos   35u  IPv4 0x3ab0a036b898b4bf      0t0  TCP 10.33.17.24:49380->wr-in-f108.1e100.net:993 (ESTABLISHED)
Mail      2414 smaintos   58u  IPv4 0x3ab0a036b897325f      0t0  TCP 10.33.17.24:49382->wr-in-f108.1e100.net:993 (ESTABLISHED)
Mail      2414 smaintos   62u  IPv4 0x3ab0a036b897325f      0t0  TCP 10.33.17.24:49382->wr-in-f108.1e100.net:993 (ESTABLISHED)
Mail      2414 smaintos   63u  IPv4 0x3ab0a036b897dc3f      0t0  TCP 10.33.17.24:49383->wr-in-f108.1e100.net:993 (ESTABLISHED)
Mail      2414 smaintos   64u  IPv4 0x3ab0a036b897dc3f      0t0  TCP 10.33.17.24:49383->wr-in-f108.1e100.net:993 (ESTABLISHED)

voir mail procotol pcap
```
Riot Client.exe

```
sudo lsof -P -a -i4 -i6 -itcp
 
RiotClien 2545 smaintos   11u  IPv4 0x3ab0a036b8983fcf      0t0  TCP 10.33.17.24:49403->104.16.56.40:443 (CLOSED)
RiotClien 2545 smaintos   13u  IPv4 0x3ab0a036b8973d6f      0t0  TCP 10.33.17.24:49410->162.247.241.1:443 (CLOSE_WAIT)
RiotClien 2545 smaintos   14u  IPv4 0x3ab0a036b897487f      0t0  TCP 10.33.17.24:49411->162.247.241.1:443 (CLOSE_WAIT)
RiotClien 2545 smaintos   22u  IPv4 0x3ab0a036b8977fcf      0t0  TCP 10.33.17.24:49432->104.16.56.40:443 (ESTABLISHED)
RiotClien 2545 smaintos   25u  IPv4 0x3ab0a036b898087f      0t0  TCP 10.33.17.24:49433->162.247.241.1:443 (ESTABLISHED)
RiotClien 2545 smaintos   31u  IPv4 0x3ab0a036b89829af      0t0  TCP localhost:49434 (LISTEN)
RiotClien 2545 smaintos   41u  IPv4 0x3ab0a036baf1112f      0t0  TCP 10.33.17.24:49453->162.247.241.1:443 (ESTABLISHED)
RiotClien 2545 smaintos   65u  IPv4 0x3ab0a036baf11c3f      0t0  TCP 10.33.17.24:49454->104.16.56.40:443 (ESTABLISHED)
RiotClien 2545 smaintos   67u  IPv4 0x3ab0a036baf1487f      0t0  TCP 10.33.17.24:49449->a96-16-122-83.deploy.static.akamaitechnologies.com:443 (ESTABLISHED)
RiotClien 2545 smaintos   68u  IPv4 0x3ab0a036b89834bf      0t0  TCP localhost:49439->localhost:49437 (ESTABLISHED)
RiotClien 2545 smaintos   69u  IPv4 0x3ab0a036b89774bf      0t0  TCP localhost:49434->localhost:49438 (ESTABLISHED)
RiotClien 2545 smaintos   70u  IPv4 0x3ab0a036baf1538f      0t0  TCP 10.33.17.24:49450->a96-16-122-83.deploy.static.akamaitechnologies.com:443 (ESTABLISHED)
RiotClien 2545 smaintos   71u  IPv4 0x3ab0a036baf174bf      0t0  TCP 10.33.17.24:49455->162.247.241.10:443 (ESTABLISHED)
RiotClien 2545 smaintos   72u  IPv4 0x3ab0a036b895487f      0t0  TCP localhost:49434->localhost:49460 (ESTABLISHED)
RiotClien 2545 smaintos   73u  IPv4 0x3ab0a036b8955e9f      0t0  TCP localhost:49434->localhost:49461 (ESTABLISHED)
RiotClien 2545 smaintos   74u  IPv4 0x3ab0a036baf17fcf      0t0  TCP 10.33.17.24:49456->104.16.56.40:443 (ESTABLISHED)
RiotClien 2545 smaintos   75u  IPv4 0x3ab0a036b896bfcf      0t0  TCP localhost:49434->localhost:49464 (ESTABLISHED)
RiotClien 2545 smaintos   76u  IPv4 0x3ab0a036baf15e9f      0t0  TCP 10.33.17.24:49451->a96-16-122-83.deploy.static.akamaitechnologies.com:443 (ESTABLISHED)
RiotClien 2545 smaintos   77u  IPv4 0x3ab0a036baf169af      0t0  TCP 10.33.17.24:49452->a96-16-122-83.deploy.static.akamaitechnologies.com:443 (ESTABLISHED)
RiotClien 2545 smaintos   78u  IPv4 0x3ab0a036b896a9af      0t0  TCP 10.33.17.24:49466->a96-16-122-83.deploy.static.akamaitechnologies.com:80 (ESTABLISHED)
RiotClien 2556 smaintos   11u  IPv4 0x3ab0a036b8983fcf      0t0  TCP 10.33.17.24:49403->104.16.56.40:443 (CLOSED)
RiotClien 2556 smaintos   13u  IPv4 0x3ab0a036b8973d6f      0t0  TCP 10.33.17.24:49410->162.247.241.1:443 (CLOSE_WAIT)
RiotClien 2556 smaintos   14u  IPv4 0x3ab0a036b897487f      0t0  TCP 10.33.17.24:49411->162.247.241.1:443 (CLOSE_WAIT)
RiotClien 2556 smaintos   22u  IPv4 0x3ab0a036b8977fcf      0t0  TCP 10.33.17.24:49432->104.16.56.40:443 (ESTABLISHED)
RiotClien 2556 smaintos   25u  IPv4 0x3ab0a036b898087f      0t0  TCP 10.33.17.24:49433->162.247.241.1:443 (ESTABLISHED)
RiotClien 2556 smaintos   41u  IPv4 0x3ab0a036b897e74f      0t0  TCP 10.33.17.24:49435->104.18.157.37:443 (CLOSE_WAIT)
RiotClien 2556 smaintos   75u  IPv4 0x3ab0a036b8953d6f      0t0  TCP localhost:49460->localhost:49434 (ESTABLISHED)
RiotClien 2556 smaintos   81u  IPv4 0x3ab0a036b8965c3f      0t0  TCP localhost:49464->localhost:49434 (ESTABLISHED)
RiotClien 2556 smaintos   83u  IPv4 0x3ab0a036b895538f      0t0  TCP localhost:49461->localhost:49434 (ESTABLISHED)
RiotClien 2556 smaintos   84u  IPv4 0x3ab0a036b8969e9f      0t0  TCP 10.33.17.24:49465->a96-16-122-83.deploy.static.akamaitechnologies.com:443 (ESTABLISHED)
RiotClien 2558 smaintos   11u  IPv4 0x3ab0a036b8983fcf      0t0  TCP 10.33.17.24:49403->104.16.56.40:443 (CLOSED)
RiotClien 2558 smaintos   13u  IPv4 0x3ab0a036b8973d6f      0t0  TCP 10.33.17.24:49410->162.247.241.1:443 (CLOSE_WAIT)
RiotClien 2558 smaintos   14u  IPv4 0x3ab0a036b897487f      0t0  TCP 10.33.17.24:49411->162.247.241.1:443 (CLOSE_WAIT)
RiotClien 2558 smaintos   22u  IPv4 0x3ab0a036b8977fcf      0t0  TCP 10.33.17.24:49432->104.16.56.40:443 (ESTABLISHED)
RiotClien 2558 smaintos   25u  IPv4 0x3ab0a036b898087f      0t0  TCP 10.33.17.24:49433->162.247.241.1:443 (ESTABLISHED)
RiotClien 2558 smaintos   33u  IPv4 0x3ab0a036b89769af      0t0  TCP localhost:49437 (LISTEN)
RiotClien 2558 smaintos   36u  IPv4 0x3ab0a036baf1325f      0t0  TCP localhost:49438->localhost:49434 (ESTABLISHED)
RiotClien 2558 smaintos   37u  IPv4 0x3ab0a036baf1274f      0t0  TCP localhost:49437->localhost:49439 (ESTABLISHED)
RiotClien 2558 smaintos   38u  IPv4 0x3ab0a036b8975e9f      0t0  TCP 10.33.17.24:49441->162.247.241.1:443 (ESTABLISHED)
RiotClien 2558 smaintos   41u  IPv4 0x3ab0a036b897e74f      0t0  TCP 10.33.17.24:49435->104.18.157.37:443 (CLOSE_WAIT)
```

Plan (application d'apple)

```
voir plan protocol pcap
```

### II. Mise en place ###

**1.SSH**

(voir pcap présent dans le github)

**Connexion ssh depuis l'ordi :**

```
➜  ~ git:(main) ✗ netstat
Active Internet connections
Proto Recv-Q Send-Q  Local Address          Foreign Address        (state)    
tcp4       0      0  172.16.40.1.49177      172.16.40.4.ssh        ESTABLISHED
```

**Connexion ssh depuis la vm :**

```
[smaintos@node1 ~]$ ss | grep ssh
tcp   ESTAB  0      0                      172.16.40.4:ssh        172.16.40.1:49177  
``` 

**2.Routage** 

(rien à mettre dans le rendu)

### III.DNS ###

```
[smaintos@dns1 ~]$ sudo cat /etc/named.conf
//
// named.conf
//
// Provided by Red Hat bind package to configure the ISC BIND named(8) DNS
// server as a caching only nameserver (as a localhost DNS resolver only).
//
// See /usr/share/doc/bind*/sample/ for example named configuration files.
//

options {
        listen-on port 53 { 127.0.0.1; any; };
        listen-on-v6 port 53 { ::1; };
        directory       "/var/named";
        dump-file       "/var/named/data/cache_dump.db";
        statistics-file "/var/named/data/named_stats.txt";
        memstatistics-file "/var/named/data/named_mem_stats.txt";
        secroots-file   "/var/named/data/named.secroots";
        recursing-file  "/var/named/data/named.recursing";
        allow-query     { localhost; any; };
        allow-query-cache { localhost; any; };

        recursion yes;

        dnssec-validation yes;

        managed-keys-directory "/var/named/dynamic";
        geoip-directory "/usr/share/GeoIP";

        pid-file "/run/named/named.pid";
        session-keyfile "/run/named/session.key";

        /* https://fedoraproject.org/wiki/Changes/CryptoPolicy */
        include "/etc/crypto-policies/back-ends/bind.config";
};

logging {
        channel default_debug {
                file "data/named.run";
                severity dynamic;
        };
};

zone "tp4.b1" IN {
     type master;
     file "tp4.b1.db";
     allow-update { none; };
     allow-query {any; };
};
zone "1.4.10.in-addr.arpa" IN {
     type master;
     file "tp4.b1.rev";
     allow-update { none; };
     allow-query { any; };
};
```

```
[smaintos@dns1 ~]$ sudo cat /var/named/tp4.b1.db
TTL 86400
@ IN SOA dns-server.tp4.b1. admin.tp4.b1. (
    2019061800 ;Serial
    3600 ;Refresh
    1800 ;Retry
    604800 ;Expire
    86400 ;Minimum TTL
)

@ IN NS dns-server.tp4.b1.

dns-server IN A 10.4.1.201
node1      IN A 10.4.1.11
[elbatista@dns-server ~]$
```

```
[smaintos@dns1 ~]$ sudo cat /var/named/tp4.b1.rev
TTL 86400
@ IN SOA dns-server.tp4.b1. admin.tp4.b1. (
    2019061800 ;Serial
    3600 ;Refresh
    1800 ;Retry
    604800 ;Expire
    86400 ;Minimum TTL
)

@ IN NS dns-server.tp4.b1.

201 IN PTR dns-server.tp4.b1.
11 IN PTR node1.tp4.b1.
```