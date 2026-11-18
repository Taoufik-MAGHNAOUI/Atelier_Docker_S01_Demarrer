# Notes – Atelier Docker S01

## La commande clé

```bash
docker run -d -p 8080:80 --name mon-site httpd:2.4
```

| Élément | Rôle |
| --- | --- |
| `docker` | appel du programme |
| `run` | création + démarrage du conteneur |
| `-d` | mode *daemon* : le conteneur tourne en arrière-plan |
| `-p 8080:80` | port `8080` de la machine hôte → port `80` interne au conteneur |
| `--name mon-site` | nom donné au conteneur |
| `httpd:2.4` | image utilisée (Apache HTTP Server 2.4, Docker Hub) |

Première réponse du système :

```
Unable to find image 'httpd:2.4' locally
```

L'image n'existe pas en local : Docker la télécharge depuis Docker Hub, puis crée et démarre le conteneur.

## Ports

On dispose de 65 535 ports. Le chiffre de gauche est le port de l'hôte, celui de droite le port interne du conteneur — un conteneur est une machine à part entière, avec son propre système, ses logiciels et ses ports.

## Image / conteneur

| Fichier | Exécution |
| --- | --- |
| image | conteneur (docker) |
| programme | processus |
| classe | objet |
| plan d'architecte | maison |

On peut construire autant de maisons que l'on veut à partir d'un plan, tant qu'on ne met pas deux maisons sur la même parcelle. De même, on peut lancer autant de conteneurs que l'on veut à partir d'une image, tant que deux conteneurs ne partagent pas le même port.

## Résultat

- Conteneur `mon-site` démarré, port `8080` publié, page personnalisée.
- `bash verifier.sh` : **8 / 8** points validés.
