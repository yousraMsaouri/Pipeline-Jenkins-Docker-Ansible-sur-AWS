pipeline {
    agent any

    stages {
        stage('📥 Cloner le dépôt GitHub') {
            steps {
                echo 'Clonage en cours...'
                // Jenkins clone automatiquement depuis GitHub grâce au Webhook
            }
        }

        stage('⚙️ Build') {
            steps {
                echo 'Construction du projet...'
                sh 'ls -l'  // Liste les fichiers pour vérif
            }
        }

        stage('🚀 Déploiement') {
            steps {
                echo 'Déploiement local sur le serveur EC2...'
                // Ex : Copie du index.html vers un dossier exposé par Apache/Nginx
                sh 'sudo cp index.html /var/www/html/index.html'
            }
        }
    }
}
