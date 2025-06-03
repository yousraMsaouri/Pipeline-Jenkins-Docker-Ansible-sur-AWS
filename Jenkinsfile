pipeline {
    agent any

    stages {
        stage('Cloner le dépôt') {
            steps {
                echo '📥 Clonage du dépôt GitHub...'
                // Jenkins clone automatiquement ton repo avec le webhook
            }
        }

        stage('Build') {
            steps {
                echo '⚙️ Construction du projet...'
                sh 'docker build -t mon-site-web:latest .' // Construit l'image Docker avec index.html
            }
        }

        stage('Deploy') {
            steps {
                echo '🚀 Déploiement en cours...'
                // Stop et supprime l'ancien conteneur s'il existe
                sh 'docker stop mon-site-web || true'
                sh 'docker rm mon-site-web || true'
                // Lance le nouveau conteneur
                sh 'docker run -d -p 80:80 --name mon-site-web mon-site-web:latest'
            }
        }
    }
}
