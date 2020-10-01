pipeline {
         agent any
         stages {
                 stage('Checkout') {
                 steps {
                     checkout([$class: 'GitSCM', branches: [[name: '*/Jenkinsfile_test']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[credentialsId: 'aws_ssh_keys', url: 'git@github.com:posttokrish/remote_add_origin.git']]])
                     sh 'echo "Hello this is Checkouut"'
                     sh 'pwd;ls -lR'
                 }
                 }
                 stage('Build') {
                 steps {
                     echo 'Hello this is stage Build'
                     sh 'sudo docker build -t my-apache3 .'
                 }
                 }
                 stage('Run') {
                     
                 steps {
                  
                 sh 'sudo docker ps | grep my-running-app-2 && sudo docker stop my-running-app-2;sudo docker rm my-running-app-2 || echo "No container "'
                 sh 'sudo docker run -dit --name my-running-app-2 -p 8082:80 my-apache3'

                 }
                 }
        
    }
}
