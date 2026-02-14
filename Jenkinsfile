pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building the project...'
                // Your build commands here, e.g. sh 'make' or bat 'build.bat'
            }
        }

        stage('Test') {
            steps {
                echo 'Running tests...'
                // Your test commands here
            }
        }
    }

    post {
        success {
            echo 'Build succeeded!'
            // Example: archive artifacts
            archiveArtifacts artifacts: '**/target/*.jar', allowEmptyArchive: true

            // Example: send email notification (requires Mailer plugin and config)
            // mail to: 'team@example.com', subject: 'Build Success', body: 'The build succeeded!'
        }
        failure {
            echo 'Build failed!'
            // You can add notifications or cleanup here
        }
        always {
            echo 'This always runs, regardless of build status'
            // Example: clean workspace
            cleanWs()
        }
    }
}