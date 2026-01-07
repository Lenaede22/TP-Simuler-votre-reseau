\# Plan d’adressage et configuration IP



Ce document décrit le plan d’adressage IP mis en place pour la maquette réseau ainsi que la configuration des périphériques finaux.



---



\## Plan d’adressage



Chaque service de la métropole dispose de son propre sous-réseau en `/24`, afin d’assurer une séparation logique claire et une meilleure organisation du réseau.



| Groupe / Service   | Réseau          | Passerelle      |

|--------------------|-----------------|------------------|

| Direction          | 192.168.20.0/24 | 192.168.20.254   |

| Examen / Concours  | 192.168.21.0/24 | 192.168.21.254   |

| Paie / DRH         | 192.168.22.0/24 | 192.168.22.254   |

| Emploi             | 192.168.23.0/24 | 192.168.23.254   |

| Médecine           | 192.168.24.0/24 | 192.168.24.254   |

| Assurance          | 192.168.25.0/24 | 192.168.25.254   |

| Info / RGPD        | 192.168.27.0/24 | 192.168.27.254   |

| Serveurs           | 192.168.30.0/24 | 192.168.30.254   |

| Imprimantes        | 192.168.40.0/24 | 192.168.40.254   |



---



\## Configuration des postes utilisateurs (PC)



Pour chaque service, les premières adresses disponibles du sous-réseau ont été attribuées aux postes utilisateurs.



Exemple :

\- PC1 : `.1`

\- PC2 : `.2`

\- Passerelle : `.254`



Les adresses IP, masques et passerelles ont été configurés manuellement sur chaque poste.



---



\## Configuration des imprimantes



Les imprimantes sont regroupées dans un sous-réseau dédié (`192.168.40.0/24`), avec une adresse IP statique par équipement.



\- Masque : `255.255.255.0`

\- Passerelle : `192.168.40.254`



---



\## Configuration des serveurs



Les serveurs (AD, applicatif, fichiers) sont placés dans le sous-réseau `192.168.30.0/24` et disposent d’adresses IP statiques afin de garantir leur accessibilité.



---



\## Validation



La cohérence du plan d’adressage a été vérifiée à l’aide de tests de connectivité (ping) entre les postes, les passerelles et les serveurs.



