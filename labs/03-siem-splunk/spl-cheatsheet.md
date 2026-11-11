# Cheat-sheet SPL

| Commande | Rôle | Exemple |
|---|---|---|
| `search` | Filtrer par mots-clés | `index="main" EventCode=4625` |
| `fields` | Garder ou retirer des champs | `... \| fields - User` |
| `table` | Afficher en tableau | `... \| table _time, host, Image` |
| `rename` | Renommer un champ | `... \| rename Image as Process` |
| `dedup` | Supprimer les doublons | `... \| dedup Image` |
| `sort` | Trier | `... \| sort - _time` |
| `stats` | Calculer des statistiques | `... \| stats count by host` |
| `eval` | Créer ou modifier un champ | `... \| eval p=lower(Image)` |
| `rex` | Extraire avec une expression régulière | `... \| rex field=Image "(?<file>[^\\]+)$"` |
| `lookup` | Enrichir avec un fichier CSV | `... \| lookup malware_lookup.csv filename` |

## Ma méthode
Commencer large, restreindre par index et type de source,
puis ajouter une commande à la fois en vérifiant le résultat.
