# Database Connection Checker

Petite application Flask qui affiche l'état de la connexion à une base MySQL/MariaDB :

- `Database Connection Status: Connected`
- `Database Connection Status: Disconnected`

## Configuration

Variables d'environnement (valeurs par défaut entre parenthèses) :

| Variable      | Description            |
|---------------|------------------------|
| `DB_HOST`     | Hôte de la base (`localhost`) |
| `DB_USER`     | Utilisateur (`root`)   |
| `DB_PASSWORD` | Mot de passe (vide)    |
| `DB_NAME`     | Nom de la base (`test`) |

## Lancer l'application

### En local (Python 3.13)

```bash
python -m venv .venv
source .venv/bin/activate        # Windows : .venv\Scripts\activate
pip install -r requirements.txt
DB_HOST=localhost DB_USER=root DB_PASSWORD=secret DB_NAME=test python app.py
```

L'application écoute sur http://localhost:5000.

### Avec Docker

```bash
docker build -t db-checker .
docker run --rm -p 5000:5000 \
  -e DB_HOST=host.docker.internal -e DB_USER=root \
  -e DB_PASSWORD=secret -e DB_NAME=test \
  db-checker
```
