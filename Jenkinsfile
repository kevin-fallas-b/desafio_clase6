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
      
      stage('SAST') {
            steps {
                echo 'npm run sonar'
            }
        }

        stage('Build') {
            steps {
                sh 'npm run build'
            }
        }

        stage('Initialize Web Server') {
            steps {
                echo 'service nginx start'
            }
        }

        stage('Deploy Application') {
            steps {
                sh 'cp dist/clase6/* /usr/share/nginx/html'
            }
        }
    }
}
