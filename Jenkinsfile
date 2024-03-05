pipeline {
    agent any
    stages {
            stage('Clone repository') {
                step {
                   checkout([$class: 'GitSCM',
                   branches: [[name: '*/main']],
                   userRemoteConfigs: [[url: 'https://github.com/rxhxt3/PES2UG21CS920_Jenkins.git']]])
                }
            }
        stage('Build') {
            steps {
                build 'PES2UG21C920-1'
                sh 'g++ main.cpp -o output'
            }
        }
        stage('Test') {
            steps {
                sh './output'
              }
        }
        stage('Deploy') {
            steps {
                echo 'deploy'
            }
        }
    }
    post{
        failure{
            error 'Pipeline failed'
        }
    }
}  
              
