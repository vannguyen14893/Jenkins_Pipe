pipeline {
    agent {
        docker {
            image 'maven:3.8.1-adoptopenjdk-11'
        }
    }
    stages {

        stage('Build') {
                 steps {
                        sh """
                        mvn clean install
                        mv /var/lib/jenkins/workspace/jenkin_pipe_multi_branch_test/target/demo.jar /home/ndvan/java/test
                        java -jar /home/ndvan/java/test/demo.jar
                        """
                  }
         }
    }
}

