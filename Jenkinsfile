pipeline{
    agent any
    stages{
        stage('Clone'){
            steps {
                git 'https://github.com/xuankien547/html.git'
            }
        }
        stage('Buid docker file'){
            steps {
                    sh 'docker build -f ./Dockerfile.nginx -t nginx:v1 .'
                    sh 'docker build -f ./Dockerfile.php -t php:v1 .'
                }
                
            }

        }
    }    
    
