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
                // Uncomment below line to simulate failure
                // sh 'exit 1'
            }
        }

        stage('Package') {
            steps {
                sh 'mkdir output'
                sh 'echo "Build file" > output/app.txt'
                archiveArtifacts artifacts: 'output/*'
            }
        }
    }
}
