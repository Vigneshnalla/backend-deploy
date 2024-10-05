pipeline {
    agent {
        label 'AGENT-1'
    }
    options {
        timeout(time: 30, unit: 'MINUTES')
        disableConcurrentBuilds()
    }
    parameters {
        string(name: 'appVersion', defaultValue: '1.5.0', description: 'What is the app version?')
    }
    environment {
        nexusUrl = 'nexus.vigneshdev.online:8081' // Nexus URL with port
    }
    stages {
        stage('Read the Version') {
            steps {
                script {
                    // Access the appVersion parameter correctly
                    echo "Application Version: ${params.appVersion}"
                }
            }
        }
        // You can add more stages here as needed
    }
    post {
        always {
            echo "I always run"
            deleteDir() // Clean up workspace
        }
    }
}
