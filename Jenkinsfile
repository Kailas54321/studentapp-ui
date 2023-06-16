pipeline {
    agent any
    
    stages {
        stage('Build stage') {
            steps {
                sh 'sudo apt-get update -y '
                sh 'sudo apt-get install maven -y'
                sh 'mvn clean package'
                sh 'sudo mkdir -p /artifact > /dev/null && sudo chown jenkins: /artifact'
                sh 'sudo mv  /var/lib/jenkins/workspace/${JOB_NAME}/target/studentapp-2.2-SNAPSHOT.war /artifact/student-${BUILD_ID}.war'
            }
        }
        
    //     stage('Test') {
    //         steps {
    //             // Run tests
    //             sh 'npm test'
    //         }
    //     }
        
    //     stage('Deploy') {
    //         steps {
    //             // Deploy the application
    //             sh 'npm run deploy'
    //         }
    //     }
    // }
    
    // post {
    //     success {
    //         // Send a notification on success
    //         echo 'Deployment successful. Sending notification...'
    //         // Implement notification mechanism here (e.g., sending an email, Slack message, etc.)
    //     }
        
    //     failure {
    //         // Send a notification on failure
    //         echo 'Deployment failed. Sending notification...'
    //         // Implement notification mechanism here (e.g., sending an email, Slack message, etc.)
    //     }
    }
}
