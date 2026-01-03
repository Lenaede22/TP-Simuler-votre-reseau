# TP-Simuler-votre-reseau
Projet réalisé dans le cadre du cours “Simuler votre réseau” sur OpenClassrooms.   L’objectif est de concevoir et configurer un réseau d’entreprise complet sous Cisco Packet Tracer.
🖧 Configuration IP des périphériques finaux

Dans ce projet, nous commençons par configurer tous les périphériques finaux avant de passer aux équipements d’interconnexion.
Nous devons donc attribuer une adresse IP correcte à :

. Les ordinateurs PC

. Les imprimantes

. Les serveurs

La configuration réseau repose sur un plan d’adressage complet, déjà pensé pour organiser la métropole en plusieurs services.

 Plan d’adressage de la métropole

Chaque service dispose de son propre sous-réseau /24.
Voici le résumé des adresses utilisées :

## Plan d’adressage de la métropole

| Groupe / Service   | Réseau          | Première adresse | Dernière adresse | Passerelle      |
|--------------------|-----------------|------------------|------------------|------------------|
| Direction          | 192.168.20.0/24 | 192.168.20.1     | 192.168.20.253   | 192.168.20.254   |
| Examen / Concours  | 192.168.21.0/24 | 192.168.21.1     | 192.168.21.253   | 192.168.21.254   |
| Paie / DRH         | 192.168.22.0/24 | 192.168.22.1     | 192.168.22.253   | 192.168.22.254   |
| Emploi             | 192.168.23.0/24 | 192.168.23.1     | 192.168.23.253   | 192.168.23.254   |
| Médecine           | 192.168.24.0/24 | 192.168.24.1     | 192.168.24.253   | 192.168.24.254   |
| Assurance          | 192.168.25.0/24 | 192.168.25.1     | 192.168.25.253   | 192.168.25.254   |
| Info / RGPD        | 192.168.27.0/24 | 192.168.27.1     | 192.168.27.253   | 192.168.27.254   |
| Serveurs           | 192.168.30.0/24 | 192.168.30.1     | 192.168.30.253   | 192.168.30.254   |
| Imprimantes        | 192.168.40.0/24 | 192.168.40.1     | 192.168.40.253   | 192.168.40.254   |


 Configuration des PC

Chaque service possède deux postes utilisateurs, auxquels nous attribuons les premières adresses disponibles.


| Groupe / Service   | PC1              | PC2              | Passerelle        |
|--------------------|------------------|------------------|-------------------|
| Direction          | 192.168.20.1/24  | 192.168.20.2/24  | 192.168.20.254    |
| Examen / Concours  | 192.168.21.1/24  | 192.168.21.2/24  | 192.168.21.254    |
| Paie / DRH         | 192.168.22.1/24  | 192.168.22.2/24  | 192.168.22.254    |
| Emploi             | 192.168.23.1/24  | 192.168.23.2/24  | 192.168.23.254    |
| Médecine           | 192.168.24.1/24  | 192.168.24.2/24  | 192.168.24.254    |
| Assurance          | 192.168.25.1/24  | 192.168.25.2/24  | 192.168.25.254    |
| Info / RGPD        | 192.168.27.1/24  | *(pas de PC2)*   | 192.168.27.254    |

 Configuration des imprimantes

Les imprimantes sont regroupées dans un sous-réseau dédié : 192.168.40.0/24.


| Imprimante | Adresse IP     | Masque          | Passerelle        |
|------------|----------------|------------------|-------------------|
| Imp-Dir    | 192.168.40.1   | 255.255.255.0    | 192.168.40.254    |
| Imp-Exam   | 192.168.40.2   | 255.255.255.0    | 192.168.40.254    |
| Imp-Paie   | 192.168.40.3   | 255.255.255.0    | 192.168.40.254    |
| Imp-Emp    | 192.168.40.4   | 255.255.255.0    | 192.168.40.254    |
| Imp-Med    | 192.168.40.5   | 255.255.255.0    | 192.168.40.254    |
| Imp-Assu   | 192.168.40.6   | 255.255.255.0    | 192.168.40.254    |
| Imp-Info   | 192.168.40.7   | 255.255.255.0    | 192.168.40.254    |


 Configuration des serveurs

Les serveurs sont placés dans le sous-réseau dédié : 192.168.30.0/24


| Serveur           | Adresse IP        | Masque          | Passerelle        |
|-------------------|--------------------|------------------|-------------------|
| Serveur-AD        | 192.168.30.1/24    | 255.255.255.0    | 192.168.30.254    |
| Serveur-Appli     | 192.168.30.2/24    | 255.255.255.0    | 192.168.30.254    |
| Serveur-Fichiers  | 192.168.30.3/24    | 255.255.255.0    | 192.168.30.254    |



Dans Packet Tracer :

Après avoir configuré l’ensemble des périphériques (PC, imprimantes et serveurs), des tests de connectivité ont été effectués à l’aide de la commande :

ping <adresse_IP_cible>


Exemples de tests réalisés :

ping 192.168.20.254   # passerelle du réseau Direction
ping 192.168.30.1     # Serveur AD
ping 192.168.40.3     # Imprimante Paie

 Résultat

Tous les tests ont répondu positivement, confirmant que :

les adresses IP ont été correctement attribuées,

les passerelles sont accessibles,

la communication entre les périphériques finaux fonctionne normalement.

La phase d’adressage IP est donc validée et opérationnelle.
