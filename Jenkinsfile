pipeline {
    agent any
    
    stages {
        stage('Build') {
            steps {
                // // Checkout source code from version control
                // git 'https://github.com/example/repository.git'
                
                // // Build the application
                sh 'mvn clean package'
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
