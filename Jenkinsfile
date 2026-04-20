pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/Deepika-2312/Jenekins-demo.git'
            }
        }

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
    }
}
