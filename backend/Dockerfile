# Utiliser une image Python allégée pour le backend
FROM python:3.9-slim

# Définir la variable d'environnement pour désactiver les buffers Python
ENV PYTHONUNBUFFERED 1

# Créer un répertoire de travail
WORKDIR /app

# Copier et installer les dépendances Python
COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

# Copier l'ensemble du code source dans le conteneur
COPY . /app

# Exposer le port 8011 (choisi pour le backend Django)
EXPOSE 8011

# Commande de démarrage avec Gunicorn
CMD ["gunicorn", "--bind", "0.0.0.0:8011", "backend.wsgi:application"]
