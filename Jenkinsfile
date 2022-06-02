pipeline {
    agent any

    stages {
        stage('Install Dependencies') {
            steps {
                sh 'npm install'
            }
        }

        stage('Unit Tests') {
            steps {
                echo 'Ejecutando unit tests'
            }
        }

        stage('Build') {
            steps {
                sh 'npm run build'
            }
        }

        stage('Initialize Web Server') {
            steps {
                sh 'service nginx start'
            }
        }

        stage('Remove old files') {
            steps {
                sh 'rm /var/www/html/index.nginx-debian.html'
            }
        }

        stage('Deploy Application') {
            steps {
                sh 'cp dist/desafio_clase6/* /var/www/html/'
            }
        }
    }
}
