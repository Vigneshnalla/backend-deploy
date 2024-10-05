pipeline {
    agent {
        label 'AGENT-1'
    }
    options {
        timeout(time: 30, unit: 'MINUTES')
        disableConcurrentBuilds()
    }
    parameters{
        string(name: 'appVersion', defaultValue: '1.5.0', description: 'what is the appVersioin')
    }
    environment {
        // Initialize appVersion as an empty string
        appVersion = ''
        nexusUrl='nexus.vigneshdev.online:8081'

    }
    stages {
        stage('Read the Version') {
            steps {
              script{
                echo "Appllication Version ${params.appVersioin}"
              }
            }
        }

      


    }
    post {
        always {
            echo "I always run"
            deleteDir() // Fixed method call from 'delete dir)()' to 'deleteDir()'
        }
    }
}
