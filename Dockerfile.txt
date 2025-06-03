# Image de base : Nginx pour servir notre index.html
FROM nginx:alpine

# Copier notre fichier HTML dans le dossier servi par nginx
COPY index.html /usr/share/nginx/html/index.html
