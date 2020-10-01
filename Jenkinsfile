pipeline {
         agent any
         stages {
                 stage('One') {
                 steps {
                     echo 'Hello this is ste=age 1'
                 }
                 }
                 stage('Two') {
                 steps {
                     echo 'Hello this is ste=age 2'
                 }
                 }
                 stage('Three') {
                 when {
                       not {
                            branch "master"
                       }
                 }
                 steps {
                       echo "Hello"
                 }
        }
    }
}
