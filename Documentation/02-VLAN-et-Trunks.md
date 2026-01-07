\# VLAN et liaisons Trunk



Ce document présente la future mise en place de la segmentation du réseau à l’aide de VLAN, ainsi que la configuration des liaisons trunk entre les équipements d’interconnexion.



---



\## Objectif



L’objectif de cette étape est de :

\- segmenter le réseau en plusieurs VLAN afin d’isoler les différents services,

\- limiter les domaines de broadcast,

\- améliorer la sécurité et la lisibilité de l’architecture réseau.



---



\## Principe des VLAN



Un VLAN (Virtual Local Area Network) permet de créer plusieurs réseaux logiques indépendants sur une même infrastructure physique.



Chaque service de l’entreprise pourra être associé à un VLAN distinct (Direction, RH, Médecine, etc.), même si les postes sont connectés aux mêmes switches.



---



\## Liaisons Trunk



Les liaisons trunk permettent de transporter le trafic de plusieurs VLAN sur un même lien physique entre :

\- les switches d’accès,

\- les switches de distribution,

\- les équipements de niveau 3.



Les trames sont identifiées à l’aide du marquage 802.1Q.



---



\## État d’avancement



À ce stade du projet :

\- les VLAN ne sont pas encore configurés,

\- les ports sont en configuration par défaut,

\- les liaisons trunk seront mises en place dans une étape ultérieure.



---



\## Illustrations



!\[Principe de segmentation par VLAN](../assets/vlan-principe.png)

> Capture à ajouter après configuration des VLAN.



!\[Exemple de liaison trunk](../assets/trunk-link.png)

> Capture à ajouter après configuration des trunks.



---



\## À compléter



Cette section sera complétée avec :

\- la création des VLAN,

\- l’affectation des ports en mode access,

\- la configuration des ports trunk,

\- les commandes de vérification (`show vlan`, `show interfaces trunk`).



