pipeline {
    agent {
        docker {
            image 'maven:3.8.1-adoptopenjdk-11'
        }
    }
    stages {
        stage('Build') {
        steps {
        git branchName:'master' , url: 'https://github.com/vannguyen14893/Jenkins_Pipe.git'

                     }
                    steps {
                        sh 'mvn clean install'
                    }
         }
    }
}
