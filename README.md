# 🚀 Mon Site Apache avec Docker

Ce projet est un site web statique (HTML + CSS + JavaScript) exécuté avec Apache dans un conteneur Docker.

Il démontre comment :
* Construire une image Docker personnalisée.
* Copier un site web dans Apache.
* Exposer un port pour accéder au serveur.
* Lancer un conteneur web localement.

---
![Description](docker.png)

## 📁 Structure du Projet
```text
docc/
│
├── Dockerfile
└── site/
    ├── index.html
    └── style.css
```
---
##🐳 Dockerfile
```
Dockerfile
FROM httpd:2.4
COPY site/ /usr/local/apache2/htdocs/
EXPOSE 80
CMD ["httpd-foreground"]
```
##⚙️ Installation & Exécution
----
##1️⃣ Construire l’image Docker
```Bash
docker build -t docc .
```
---
##2️⃣ Lancer le conteneur
Si le port 8080 est occupé, utilisez un autre port (ex: 5000) :

```Bash
docker run -d -p 5000:80 docc
```
##3️⃣ Accéder au site
Ouvrez votre navigateur :
👉 http://localhost:5000


