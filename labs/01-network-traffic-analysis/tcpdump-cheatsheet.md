# Cheat-sheet tcpdump

tcpdump nécessite les droits administrateur : on l'exécute avec `sudo`.

## Options principales

| Option | Rôle |
|---|---|
| `-D` | Liste les interfaces disponibles |
| `-i eth0` | Choisit l'interface à écouter |
| `-n` / `-nn` | Pas de résolution des noms d'hôtes / des ports |
| `-v`, `-vv`, `-vvv` | Augmente le niveau de détail |
| `-X` | Affiche le contenu du paquet en hexadécimal et ASCII |
| `-e` | Inclut l'en-tête Ethernet (adresses MAC) |
| `-c 100` | S'arrête après 100 paquets |
| `-w fichier.pcap` | Écrit la capture dans un fichier |
| `-r fichier.pcap` | Lit une capture depuis un fichier |

## Combinaisons que j'utilise

```bash
sudo tcpdump -i eth0 -nn -vX -c 100      # 100 paquets, sans résolution, détaillés
sudo tcpdump -i eth0 -w capture.pcap     # enregistrer
sudo tcpdump -nnvXr capture.pcap         # relire avec le détail
```

## Pièges
- Une capture longue remplit vite le disque.
- Sans `-nn`, tcpdump fait des requêtes DNS pendant la capture, ce qui ajoute du trafic.

## Ce que j'ai retenu
*Une ou deux phrases à vous.*
