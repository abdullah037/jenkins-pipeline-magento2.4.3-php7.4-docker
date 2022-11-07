pipeline {
    agent any
    stages {
        stage('Cloning Project') {
            steps {
                git 'https://gitlab.com/iabdullah1/magento2.4.3-php7.4-docker.git'
            }
        }
        stage('Setting Permissions') {
            steps {
                sh '''chmod 777 -R magento2-2.4.3'''
            }}
        stage('Setting up magento2') {
            steps {
                sh 'docker-compose up -d --build'
            }
            
        }
    }
    
}
