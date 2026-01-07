\# Routage inter-VLAN



Ce document décrit le principe et la future mise en place du routage inter-VLAN dans la maquette réseau.



---



\## Objectif



Le routage inter-VLAN permet aux équipements appartenant à des VLAN différents de communiquer entre eux.



Cette fonction est indispensable pour :

\- permettre l’accès aux serveurs,

\- assurer la communication entre services,

\- centraliser l’accès réseau via une passerelle.





\## Principe du routage inter-VLAN



Le routage inter-VLAN peut être assuré par :

\- un routeur (router-on-a-stick),

\- ou un commutateur de niveau 3.



Dans cette maquette, le routage inter-VLAN sera assuré par un \*\*switch de niveau 3\*\*, jouant le rôle de passerelle pour les différents VLAN.



Chaque VLAN disposera :

\- d’une interface logique (SVI),

\- d’une adresse IP servant de passerelle par défaut aux postes du VLAN.



---



\## État d’avancement



À ce stade :

\- le plan d’adressage est défini,

\- les VLAN ne sont pas encore routés,

\- le routage inter-VLAN sera configuré dans une étape ultérieure.



---



\## Illustrations



!\[Principe du routage inter-VLAN](../assets/inter-vlan-routing.png)

> Capture à ajouter après activation du routage inter-VLAN.



---



\## À compléter



Cette documentation sera enrichie avec :

\- la configuration des interfaces VLAN (SVI),

\- l’activation du routage IP,

\- les tests de communication entre VLAN,

\- les commandes de vérification (`show ip route`, `show ip interface brief`).



