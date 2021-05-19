String branchName = env.BRANCH_NAME
pipeline {
    agent {
        docker {
            image 'maven:3.8.1-adoptopenjdk-11'
        }
    }
    stages {
        stage('Build') {
                 steps {
                        echo 'Cloning files from (branch: "' + branchName + '" )'
                        sh 'mvn clean install'
                  }
         }
    }
}
