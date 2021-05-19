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
                        sudo mv /var/lib/jenkins/workspace/jenkin_pipe_multi_branch_test/target/demo.jar /home/ndvan/java/test
                        java -jar /home/ndvan/java/test/demo.jar
                        PID=`ps -ef | grep "demo.jar" | grep -v "grep" | awk '{print $2}'`
                        echo $PID
                        #to check PID is right

                        if [ "$PID" = "" ]
                        then
                        	echo "Starting demo.jar Service";
                        	nohup java -Xms256m -Xmx6384m -jar "dev_partner-core_2.jar">> /home/ndvan/java/test/logs/demo.out 2>&1 &
                        else
                        	echo "Service is still running. You have to stop it first."
                        fi
                        """
                  }
         }
    }
}

