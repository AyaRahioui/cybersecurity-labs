# Event IDs Windows utiles

| ID | Journal | Signification | Que chercher / pourquoi c'est suspect |
|---|---|---|---|
| 4624 | Security | Ouverture de session réussie | Heures ou sources inhabituelles ; regarder le Logon Type |
| 4625 | Security | Échec d'ouverture de session | Beaucoup d'échecs d'affilée = force brute possible |
| 4648 | Security | Connexion avec identifiants explicites | Possible mouvement latéral |
| 4672 | Security | Privilèges spéciaux attribués | Compte à privilèges qui se connecte : est-ce attendu ? |
| 4698 | Security | Tâche planifiée créée | Mécanisme classique de persistance |
| 4719 | Security | Politique d'audit modifiée | Quelqu'un cherche peut-être à masquer ses traces |
| 1102 | Security | Journal d'audit effacé | Effacement de preuves |
| 7045 | System | Service installé | Service inconnu = malware possible |
| 1074 | System | Arrêt / redémarrage demandé | Redémarrage inattendu |

## Comptes de service (`-svc`)
Un compte de service est utilisé par une application, pas par une personne.
Il est normalement non interactif : une connexion RDP avec un compte `-svc`
est donc anormale et à investiguer.

## Logon Types à connaître
2 = interactif, 3 = réseau, 5 = service, 10 = RDP.
