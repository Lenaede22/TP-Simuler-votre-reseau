\# Accès Wi-Fi sécurisé



Ce document décrit la mise en place et la validation de l’accès Wi-Fi dans la maquette réseau.



---



\## Mise en place du Wi-Fi



Un point d’accès Wi-Fi a été ajouté afin de permettre la connexion d’équipements mobiles (tablette, smartphone, objets connectés).



Les paramètres suivants ont été configurés :



\## Paramètres du réseau Wi-Fi



Le point d’accès Wi-Fi a été configuré avec les paramètres suivants :



| Nom du SSID | Sécurité sans fil | Mot de passe |

|------------|------------------|--------------|

| Metropole  | WPA2-PSK         | 1234-Metropole:1234 |



Le choix du chiffrement \*\*WPA2-PSK\*\* permet de sécuriser les communications sans fil à l’aide d’une clé partagée, tout en restant simple à mettre en œuvre dans le cadre de cette maquette.





\## Connexion des équipements mobiles



Les équipements mobiles ont été configurés pour se connecter au SSID configuré sur le point d’accès.



Une fois connectés :

\- les équipements obtiennent une adresse IP valide,

\- la passerelle par défaut est accessible,

\- la communication avec les autres équipements du réseau est possible.



---



\## Validation



Des tests de connectivité ont été réalisés depuis les équipements Wi-Fi vers :

\- la passerelle réseau,

\- les postes filaires,

\- les serveurs.



Les résultats des tests confirment le bon fonctionnement de l’accès Wi-Fi sécurisé.



