# Présentation générale du projet

Ce projet consiste en la simulation d’un réseau d’entreprise réalisée sous Cisco Packet Tracer, dans le cadre du cours « Simuler votre réseau » sur OpenClassrooms.

L’objectif est de concevoir une maquette réseau fonctionnelle, structurée par services, en respectant un plan d’adressage cohérent et en mettant en place les premières briques d’interconnexion et d’accès réseau.



État actuel du projet

À ce stade, les éléments suivants ont été réalisés :

Plan d’adressage IP



Définition d’un plan d’adressage par service, chaque groupe disposant de son propre sous-réseau en /24.

Séparation logique des réseaux pour :



Direction

Examen / Concours

Paie / DRH

Emploi

Médecine

Assurance

Info / RGPD

Serveurs

Imprimantes



Configuration des périphériques finaux



Configuration manuelle des adresses IP, masques et passerelles sur :



les postes utilisateurs (PC),

les imprimantes,

les serveurs.



Vérification de la cohérence entre les adresses configurées et le plan d’adressage défini.

Accès Wi-Fi



Mise en place d’un point d’accès Wi-Fi.

Configuration d’un SSID sécurisé en WPA2-PSK.

Connexion d’équipements mobiles (tablette, smartphone, etc.) au réseau sans fil.

Tests et dépannage



Réalisation de tests de connectivité à l’aide de la commande ping.

Identification et correction de pannes de configuration :



erreur d’adressage IP sur un poste utilisateur,

erreur de mot de passe Wi-Fi empêchant la connexion d’un équipement mobile.



Validation du rétablissement des communications après correction.



Organisation du projet

Le projet est structuré de la manière suivante :



packet-tracer/ : fichier de la maquette réseau au format .pkt.

docs/ : documentation détaillée par étape (adressage, Wi-Fi, tests, dépannage).

assets/ : captures d’écran de la topologie, des tests et des configurations.

tests/ : résultats bruts des tests de connectivité.



À compléter

Les prochaines étapes du projet incluront notamment :



la mise en place de la segmentation par VLAN,

la configuration des liaisons d’interconnexion,

le routage inter-VLAN,

des tests de validation supplémentaires et l’amélioration de la documentation.

Cette documentation sera enrichie au fur et à mesure de l’avancement du projet.



