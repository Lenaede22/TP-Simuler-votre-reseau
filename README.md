<h1 align="center">
  TP – Simuler votre réseau (Cisco Packet Tracer)
</h1>

<p align="center">
  Configuration des adresses IP des PC, imprimantes et serveurs d'une métropole virtuelle.
</p>

---

## 1. Objectif du projet

Ce projet a été réalisé dans le cadre du cours **« Simuler votre réseau »**.  
L’objectif est de configurer l’adressage IP de tous les périphériques finaux avant de passer aux équipements d’interconnexion (switchs, routeurs, VLAN, etc.).

Périphériques concernés :

- Ordinateurs **PC**
- **Imprimantes**
- **Serveurs** applicatifs / AD / fichiers

---

## 2. Plan d’adressage de la métropole

Chaque service dispose de son propre sous-réseau en `/24`.

| Groupe / Service   | Réseau            | Première adresse | Dernière adresse  | Passerelle       |
|--------------------|-------------------|------------------|-------------------|------------------|
| Direction          | 192.168.20.0/24   | 192.168.20.1     | 192.168.20.253    | 192.168.20.254   |
| Examen / Concours  | 192.168.21.0/24   | 192.168.21.1     | 192.168.21.253    | 192.168.21.254   |
| Paie / DRH         | 192.168.22.0/24   | 192.168.22.1     | 192.168.22.253    | 192.168.22.254   |
| Emploi             | 192.168.23.0/24   | 192.168.23.1     | 192.168.23.253    | 192.168.23.254   |
| Médecine           | 192.168.24.0/24   | 192.168.24.1     | 192.168.24.253    | 192.168.24.254   |
| Assurance          | 192.168.25.0/24   | 192.168.25.1     | 192.168.25.253    | 192.168.25.254   |
| Info / RGPD        | 192.168.27.0/24   | 192.168.27.1     | 192.168.27.253    | 192.168.27.254   |
| Serveurs           | 192.168.30.0/24   | 192.168.30.1     | 192.168.30.253    | 192.168.30.254   |
| Imprimantes        | 192.168.40.0/24   | 192.168.40.1     | 192.168.40.253    | 192.168.40.254   |

---

## 3. Configuration des PC

Les PC des différents services utilisent les premières adresses disponibles de chaque sous-réseau.

| Groupe / Service   | PC1               | PC2                | Passerelle        |
|--------------------|-------------------|--------------------|-------------------|
| Direction          | 192.168.20.1/24   | 192.168.20.2/24    | 192.168.20.254    |
| Examen / Concours  | 192.168.21.1/24   | 192.168.21.2/24    | 192.168.21.254    |
| Paie / DRH         | 192.168.22.1/24   | 192.168.22.2/24    | 192.168.22.254    |
| Emploi             | 192.168.23.1/24   | 192.168.23.2/24    | 192.168.23.254    |
| Médecine           | 192.168.24.1/24   | 192.168.24.2/24    | 192.168.24.254    |
| Assurance          | 192.168.25.1/24   | 192.168.25.2/24    | 192.168.25.254    |
| Info / RGPD        | 192.168.27.1/24   | *(pas de PC2)*     | 192.168.27.254    |

---

## 4. Configuration des imprimantes

Les imprimantes sont regroupées sur un sous-réseau dédié : **192.168.40.0/24**.

| Imprimante | Adresse IP     |
|------------|----------------|
| Imp-Dir    | 192.168.40.1   |
| Imp-Exam   | 192.168.40.2   |
| Imp-Paie   | 192.168.40.3   |
| Imp-Emp    | 192.168.40.4   |
| Imp-Med    | 192.168.40.5   |
| Imp-Assu   | 192.168.40.6   |
| Imp-Info   | 192.168.40.7   |

Paramètres communs :

- **Masque** : `255.255.255.0`
- **Passerelle** : `192.168.40.254`

---

## 5. Configuration des serveurs

Les serveurs sont également isolés dans leur propre sous-réseau : **192.168.30.0/24**.

| Serveur           | Adresse IP        |
|-------------------|-------------------|
| Serveur-AD        | 192.168.30.1/24   |
| Serveur-Appli     | 192.168.30.2/24   |
| Serveur-Fichiers  | 192.168.30.3/24   |

Paramètres communs :

- **Masque** : `255.255.255.0` (`/24`)
- **Passerelle** : `192.168.30.254`

---

## 6. Méthode de configuration dans Cisco Packet Tracer

Pour chaque périphérique :

1. Cliquer sur l’équipement (PC, imprimante, serveur).
2. Aller dans l’onglet **Desktop** (ou équivalent) puis **IP Configuration**.
3. Renseigner :
   - l’adresse IP
   - le masque (`255.255.255.0`)
   - la passerelle correspondant au sous-réseau

---

## 7. Vérification de la configuration

Une fois les adresses configurées, la connectivité peut être testée avec la commande :

ping <adresse_IP_cible>


Ces tests permettent de vérifier :

la bonne configuration des adresses IP,

la cohérence du plan d’adressage,

le rétablissement de la communication après correction d’erreurs.

Les résultats des tests et les scénarios de dépannage sont décrits dans le dossier tests/.
8. Tests et dépannage

Des incidents ont volontairement été introduits afin de s’exercer au dépannage réseau, notamment :

erreur de configuration d’adresse IP sur un poste utilisateur,

problème d’authentification sur le réseau Wi-Fi.

Les erreurs ont été identifiées, corrigées, puis validées par des tests de connectivité concluants.
Le détail des analyses et corrections est disponible dans le dossier docs/.

## 9. Organisation du dépôt

Le projet est structuré de la manière suivante :

```text
TP-Simuler-votre-reseau/
├── README.md        # Présentation globale du projet
├── docs/            # Documentation détaillée (adressage, Wi-Fi, dépannage)
├── packet-tracer/   # Fichiers Cisco Packet Tracer (.pkt)
├── tests/           # Résultats des tests de connectivité (ping)
├── assets/          # Captures d’écran et schémas
└── notes/           # Notes et commandes utiles
