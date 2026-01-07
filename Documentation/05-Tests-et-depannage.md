## \# Tests et dépannage du réseau



Cette section présente les tests de connectivité réalisés ainsi que les opérations de dépannage effectuées suite aux pannes introduites dans le scénario de l’exercice.



---



\## Contexte



Deux dysfonctionnements ont été identifiés :



\- La communication entre PC1 et PC2 est défaillante.

\- La communication entre la tablette Wi-Fi et les autres équipements du réseau est défaillante.



---



\## Tests initiaux



Des tests de connectivité ont été effectués à l’aide de la commande `ping`.



Résultats avant correction :

\- Ping PC1 → PC2 : échec

\- Ping tablette → réseau : échec



---



\## Dépannage n°1 : erreur d’adressage IP sur PC2



\### Analyse

La vérification de la configuration IP des postes a mis en évidence une erreur sur PC2.



Adresse configurée :



Cette adresse ne correspondait pas au sous-réseau attendu.



\### Correction

L’adresse IP a été corrigée pour correspondre au plan d’adressage :



\### Validation

Après correction :

\- Ping PC1 → PC2 : succès



---



\## Dépannage n°2 : erreur de mot de passe Wi-Fi sur la tablette



\### Analyse

La tablette tentait de se connecter au bon SSID, mais avec un mot de passe incorrect.



\### Correction

Le mot de passe Wi-Fi a été corrigé afin de correspondre à la clé WPA2-PSK configurée sur le point d’accès.



\### Validation

Après correction :

\- la tablette obtient une adresse IP valide,

\- les pings vers la passerelle et les autres équipements sont concluants.



---



\## Conclusion



Les pannes rencontrées étaient dues à des erreurs de configuration simples mais bloquantes :

\- une erreur de saisie dans une adresse IP,

\- une incohérence de clé Wi-Fi.



Le dépannage a été réalisé par une vérification méthodique des paramètres réseau, permettant de rétablir une connectivité complète entre les équipements filaires et sans fil.



