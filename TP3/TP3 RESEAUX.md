### TP3 B1-RESEAU-2022 ###

### (DEPUIS LA MAJ DE MAC OS VENTURA PLEIN DE COMMANDE BUG DANS LE TERMINAL , COMME SSH JE NE SUIS PAS LE SEUL A QUI C'EST ARRIVEF C'EST DONC POUR CELA QUE J'AI PAS PU COPIER COLLER LES RESULTAT MAIS DES SCREENSHOOT , sorry) ###
**1. Echange ARP**

**🌞Générer des requêtes ARP**

* effectuer un ping d'une machine à l'autre
* observer les tables ARP des deux machines
* repérer l'adresse MAC de john dans la table ARP de marcel et vice-versa
* prouvez que l'info est correcte (que l'adresse MAC que vous voyez dans la table est * bien celle de la machine correspondante)
  * une commande pour voir la MAC de marcel dans la table ARP de john
  * et une commande pour afficher la MAC de marcel, depuis marcel

John ping  :
![](https://i.imgur.com/PpltrQM.png)


Marcel ping : 
![](https://i.imgur.com/7ILDTSv.png)

John ARP :
![](https://i.imgur.com/dnuQIDD.png)

L'adresse mac de marcel est donc : aa:86.93.74.19.1a

Marcel ARP :   
![](https://i.imgur.com/cM2dSgF.png)

L'adresse mac de john est donc : 8e:c6:c7:e4:e7:bb

Pour prouver :  
 Depuis john : 
 ![](https://i.imgur.com/vsgAyGJ.png)

 Depuis marcel :  
 ![](https://i.imgur.com/Z7Yl2Fh.png)

**2. Analyse de trames**

**🌞Analyse de trames**

* utilisez la commande tcpdump pour réaliser une capture de trame
* videz vos tables ARP, sur les deux machines, puis effectuez un ping



### II. Routage ### 

### 1. Mise en place du routage ###

**🌞Activer le routage sur le noeud router**

![](https://i.imgur.com/B6jEcPp.png)
 
 
 (mac os , étape avant meme et apres meme on realisable)



### 3. Accès internet ###

