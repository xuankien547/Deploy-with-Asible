pipeline{
    agent any
    environment {
        docker=credentials('docker')
    }
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
        stage('Push dockerhub'){
            steps {
                sh 'docker tag nginx:v1 xuankien547/nginx:v1'
                sh 'docker tag php:v1 xuankien547/php:v1'

                sh 'echo $docker_PSW | docker login -u $docker_USR --password-stdin'
                sh 'docker push xuankien547/nginx:v1'
                sh 'docker push xuankien547/php:v1'
            }
        }

        }
    }    
    
