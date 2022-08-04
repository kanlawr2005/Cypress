pipeline {
    agent any

    tools {nodejs "node"}

    environment {
        CHROME_BIN = '/bin/google-chrome'
    }

    stages {
        stage('Dependencies') {
            steps {
               sh '''sudo su    
               visudo -f /etc/sudoers
               jenkins ALL= NOPASSWD: ALL
            }
        }
        stage('Build') {
            steps {
                sh 'sudo npx cypress run'
            }
        }
        stage('Unit Tests') {
            steps {
                sh 'sudo npm run test'
            }
        }
        stage('e2e Tests') {
            steps {
                sh 'sudo npm run cypress:ci'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
                
            }
        }
    }
}
