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
                step {
                    sh 'docker build -t nginx -f Dockerfile.nginx'
                }
                step {
                    sh 'docker build -t php -f Dockerfile.php'
                }
                
            }
        }
    }    
    }
