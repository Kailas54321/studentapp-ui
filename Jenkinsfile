pipeline {
    agent any
    
    stages {
        stage('Build stage') {
            steps {
//                 sh 'sudo apt-get update -y '
//                 sh 'sudo apt-get install maven -y'
                sh 'mvn clean package'
                sh 'sudo mkdir -p /artifact > /dev/null && sudo chown jenkins: /artifact'
                sh 'sudo mv  /var/lib/jenkins/workspace/${JOB_NAME}/target/studentapp-2.2-SNAPSHOT.war /artifact/student-${BUILD_ID}.war'
            }
        }
        stage('docker'){
        steps {
// //                 sh 'sudo apt-get install docker.io -y'
//                 sh 'sudo apt-get update -y '
//                 sh 'sudo systemctl start docker'
//                 sh 'sudo systemctl enable docker'
                sh 'cp -rv /artifact/student-${BUILD_ID}.war student-${BUILD_ID}.war'
                //sh 'echo \'FROM tomcat\\nWORKDIR /opt/tomcat/webapps/ \\nRUN apt-get install curl && RUN curl -O https://test-artifact-pritam.s3.us-east-2.amazonaws.com/student-${BUILD_ID}.war \\nEXPOSE 8080\' > dockerfile'
                sh ''' 
                cat << EOF > dockerfile
FROM tomcat:8
COPY student-${BUILD_ID}.war ./webapps/
EXPOSE 8080  
                ''' //heredocs
                sh 'cat dockerfile'
                sh 'sudo chown jenkins: /usr/bin/docker'
                sh 'sudo docker build .'
            }
        }
        
    //     failure {
    //         // Send a notification on failure
    //         echo 'Deployment failed. Sending notification...'
    //         // Implement notification mechanism here (e.g., sending an email, Slack message, etc.)
    //     }
    }
}
