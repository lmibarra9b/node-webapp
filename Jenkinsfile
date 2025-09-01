pipeline {
    agent {  
        label 'linux-node'  
    }  
    stages {
        stage('Checkout') {  
            steps {  
                git url: 'https://github.com/lmibarra9b/node-webapp.git', branch: 'main'
            }  
        }  
        stage('Build Image') {
            steps {  
                script {  
                    docker.build('node-webapp:latest')
                }
            }  
        }  
        stage('Run') {
            steps {  
                script {  
                    docker.image('node-webapp:latest').run('-d -p 3000:3000')
                }  
            }  
        }
    }  
}
