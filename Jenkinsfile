pipeline {
    agent any

    stages {
        stage('Cloner le dépôt') {
            steps {
                git 'https://github.com/nancyranou/Projet_Tchouga_B3'
            }
        }

        stage('Construire l\'image Docker') {
            steps {
                sh 'docker build -t tchouga-site .'
            }
        }

        stage('Exécuter le conteneur') {
            steps {
                sh 'docker stop tchouga || true'
                sh 'docker rm tchouga || true'
                sh 'docker run -d --name tchouga -p 8081:80 tchouga-site'
            }
        }
    }
}

