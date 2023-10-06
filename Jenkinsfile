pipeline {
    agent any

    tools {
        git 'Default'
    }

    stages {
    
        stage('Checkout1') {
        // Checkout code from the 'main' branch
            steps{
                script {
                    // Use the withCredentials step to access AWS credentials by ID
                    withCredentials([
                        usernamePassword(
                            credentialsId: '65b859fa-8c76-49a5-b70c-53b42326b02c', // Your AWS credentials ID in Jenkins
                            usernameVariable: 'AKIARGWR6CGSTJVCA2QY',
                            passwordVariable: 'CoAm9Y39uSYaApjgoYorr5Sz2cwBWurdzhn6yova'
                        )
                    ]) {

                checkout([
                    $class: 'GitSCM', 
                    branches: [[name: 'main']], 
                    doGenerateSubmoduleConfigurations: false, 
                    extensions: [],  
                    userRemoteConfigs: [[credentialsId: 'f5b950dd-c4d5-47e3-91db-144dd8f8fdc2', 
                                         url: 'https://git-codecommit.ap-south-1.amazonaws.com/v1/repos/Snapcoins']]
                        ])
                 }
    }
        
    
    
        /*
        stage('Checkout') {
            steps {
                git clone: credentialsId: 'Test', 'https://git-codecommit.ap-south-1.amazonaws.com/v1/repos/Snapcoins' 
                git switch main
            }
        }
        
        stage('Build') {
            steps {
                
                dir('client') {
                    bat 'npm install'
                    //bat 'npm test'
                }

                dir('servers/gamer-module') {
                    bat 'npm install'
                    //bat 'npm test'
                }

                dir('servers/merchant-module') {
                    bat 'npm install'
                    //bat 'npm test'
                }

                dir('servers/gaming-vendor-module') {
                    bat 'npm install'
                    //bat 'npm test'
                }

                dir('servers/general-module') {
                    bat 'npm install'
                    //bat 'npm test'
                    
                }
            }
        }

        stage('Create Docker Images'){

            steps {
                dir('client') {
                    bat 'docker build -t client-image .'
                }

                dir('servers/gamer-module') {
                    bat 'docker build -t gamer-module .'
                }

                dir('servers/merchant-module') {
                    bat 'docker build -t merchant-module .'
                }
                
                dir('servers/gaming-vendor-module') {
                    bat 'docker build -t gaming-vendor-module .'
                }

                dir('servers/general-module') {
                    bat 'docker build -t general-module .'
                }
                
            }

        }
        */
    }
}

    }
