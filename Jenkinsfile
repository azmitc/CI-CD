pipeline {
    agent any

    stages {
        stage('clean') {
            steps {
                sh 'sudo rm -rf *'
            }
        }
        stage('clone') {
            steps {
         sh 'git clone https://azmytc@bitbucket.org/azmytc/reactjsapp.git'
            }
        }
        stage('remove') {
            steps {
             sh 'cd reactjsapp && docker rm --force azmitc'  
            }
        }
        stage('Build') {
            steps {
                sh 'cd reactjsapp && docker build -t zimaa .'

            }
        }
        stage('run') {
            steps {
             sh 'docker run -it -d --name azmitc  -p 3005:3000  zimaa'
            }
        }
    }
}