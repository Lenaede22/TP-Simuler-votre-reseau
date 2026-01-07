\# Premières configurations des routeurs et sous-réseau VPN



Ce document décrit la mise en place des routeurs dans la maquette réseau ainsi que l’ajout du sous-réseau VPN destiné aux clients distants.



---



\## Rôle du routeur dans le réseau



Un routeur est un équipement d’interconnexion permettant de relier plusieurs réseaux IP distincts entre eux.  

Il assure le routage des paquets entre différents sous-réseaux et permet notamment l’interconnexion de réseaux distants via des liaisons WAN ou VPN.



Dans cette maquette, le routage est assuré par :



\- un routeur interne à l’entreprise,

\- un routeur dédié aux clients VPN,

\- un commutateur de niveau 3 (switch L3) jouant également un rôle de routage au sein du réseau interne.



---



\## Nombre de routeurs dans la topologie





Le schéma final du réseau comporte \*\*deux routeurs physiques\*\* :



\- un routeur principal situé dans l’entreprise,

\- un routeur destiné au sous-réseau VPN (clients distants).



Un \*\*troisième équipement\*\*, le switch de niveau 3, assure le routage interne entre les sous-réseaux de l’entreprise mais reste dans son état d’origine pour cette partie du projet.



---



\## Ajout du sous-réseau VPN



Un sous-réseau VPN a été ajouté afin de représenter des clients situés à l’extérieur de l’entreprise.



Ce sous-réseau comprend :

\- un routeur VPN,

\- deux postes clients,

\- une imprimante.



Ce réseau est volontairement séparé du reste de l’entreprise afin de simuler un accès distant.



---



\## Connexion WAN entre les routeurs



La liaison entre le routeur de l’entreprise et le routeur VPN est réalisée via une \*\*connexion série\*\*, représentant une liaison WAN longue distance.



Caractéristiques de la liaison :

\- Connexion de type \*\*point-à-point\*\*

\- Utilisation d’un \*\*câble série DTE/DCE\*\*

\- Ajout d’une carte \*\*WIC-2T\*\* sur les routeurs afin de disposer de ports série



Dans Cisco Packet Tracer, cette liaison est représentée graphiquement par un \*\*éclair\*\*, symbole couramment utilisé pour illustrer les connexions WAN ou VPN entre sites distants.



---



\## Plan d’adressage du sous-réseau VPN



Les équipements du sous-réseau VPN utilisent le réseau suivant : 192.168.110.0/24


Le plan d’adressage est le suivant :



| Équipement | Adresse IP | Passerelle |

|-----------|------------|------------|

| PC1-VPN   | 192.168.110.1/24 | 192.168.110.254 |

| PC2-VPN   | 192.168.110.2/24 | 192.168.110.254 |

| Imp-VPN   | 192.168.110.3/24 | 192.168.110.254 |



---



\## Configuration des périphériques finaux du VPN



Les adresses IP, masques et passerelles ont été configurés manuellement sur :

\- les deux postes clients VPN,

\- l’imprimante du sous-réseau VPN.



L’imprimante VPN n’est pas placée dans le sous-réseau Impression de l’entreprise, car elle appartient à un réseau externe distinct.



---



\## Remarque sur la DMZ et les VLAN



Le sous-réseau VPN étant composé de peu d’équipements, aucun VLAN spécifique n’a été mis en place dans cette zone.



La mise en œuvre de VLAN dans une DMZ sera abordée ultérieurement, dans des cas où le nombre de machines ou les besoins de segmentation le justifient.



---



\## État d’avancement



À ce stade :

\- le sous-réseau VPN est intégré à la topologie,

\- les équipements finaux du VPN sont correctement adressés,

\- la liaison WAN entre les routeurs est en place.



Les étapes suivantes consisteront à configurer le routage et les mécanismes de sécurité nécessaires à la communication entre le réseau interne et le sous-réseau VPN.



\### Ajout du sous-réseau VPN dans Packet Tracer



!\[Ajout du sous-réseau VPN](../assets/vpn-subnet-topology.png)









