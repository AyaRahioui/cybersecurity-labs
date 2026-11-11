# Règles de décision en triage SOC (niveau 1)

Pour chaque alerte, je me pose trois questions :
1. Qui ? (utilisateur, compte de service, admin)
2. Depuis où ? (poste d'administration dédié, serveur, poste inconnu)
3. Est-ce attendu dans cet environnement ?

| Situation observée | Décision | Raison |
|---|---|---|
| Compte de service avec ouverture de session RDP | Escalader | Ces comptes ne sont pas censés être interactifs |
| Compte désactivé qui tente de s'authentifier | Escalader | Possible réutilisation d'identifiants |
| Admin connecté depuis un poste non prévu | Vérifier auprès de l'équipe IT | Peut être une erreur de procédure ou une compromission |
| Échecs de connexion répartis sans schéma | Surveiller | Bruit possible, pas de signe de force brute |
| Connexion directe du compte `root` en SSH | Escalader | Compte normalement bloqué à distance |
