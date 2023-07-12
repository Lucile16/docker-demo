# Docker-demo

**Lucile BEUCHER**

**Commandes effectuées pour Jenkins :** <br><br>
(Sans Dockerfile)
- `docker pull jenkins/jenkins` Pour récupérer l'image sur DockerHub
- `docker run --name my-container2 -it jenkins/jenkins` Pour lancer le conteneur "my-container2"
- `docker run -p 8080:8080 -p 50000:50000 -v jenkins_home:/var/jenkins_home --name jenkins -d jenkins/jenkins` Pour l'ouvrir sur le port 8080
- Ajout d'un mot de passe administrateur donné par cette commande : `docker exec jenkins cat /var/jenkins_home/secrets/initialAdminPassword`
- Installer les plugins suggérés
- Créer un job nommé "job1"
- Dans la partie "build steps", sélectionner "Exécuter un script shell" contenant `echo "Hello world"` puis enregistrer
- Lancer le build et cliquer dessus
- Sortie de la console :

![Capture d'écran](Screenshot.png "Capture d'écran")

(Avec Dockerfile)
- `docker build -t myjenkins-blueocean:2.401.2-1 .`
- `docker run --name my-container3 -it myjenkins-blueocean:2.401.2-1`