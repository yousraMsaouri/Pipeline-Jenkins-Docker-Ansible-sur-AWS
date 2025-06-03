pipeline {
    agent any

    stages {
        stage('📥 Cloner le dépôt') {
            steps {
                echo '✔️ Dépôt cloné automatiquement par Jenkins grâce au webhook'
                sh 'ls -l'
            }
        }

        stage('⚙️ Build de l\'image Docker') {
            steps {
                echo '🔧 Construction de l’image Docker...'
                sh 'docker build -t mon-site-web-nginx .'
            }
        }

        stage('🧹 Arrêt du conteneur existant') {
            steps {
                echo '🛑 Suppression du conteneur précédent...'
                sh '''
                    docker stop mon-site-web || true
                    docker rm mon-site-web || true
                '''
            }
        }

        stage('🚀 Déploiement du nouveau conteneur') {
            steps {
                echo '🚀 Déploiement en cours sur EC2...'
                sh 'docker run -d -p 80:80 --name mon-site-web mon-site-web-nginx'
            }
        }
    }
}
