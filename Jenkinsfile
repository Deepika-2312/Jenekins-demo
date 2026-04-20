pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building the application'
            }
        }

        stage('Test') {
            steps {
                echo 'Running tests'
            }
        }

        stage('Package') {
            steps {
                bat 'mkdir output'
                bat 'echo Build file > output\\app.txt'
                archiveArtifacts artifacts: 'output/*'
            }
        }
    }
}
