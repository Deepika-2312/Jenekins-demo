pipeline {
    agent any

    parameters {
        choice(name: 'ENV', choices: ['DEV', 'QA', 'PROD'], description: 'Select Environment')
    }

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

        stage('Deploy') {
            steps {
                echo "Deploying to ${params.ENV} environment"
            }
        }

        stage('Approval') {
            when {
                expression { params.ENV == 'PROD' }
            }
            steps {
                input message: 'Approve Production Deployment?'
            }
        }
    }

    post {
        success {
            echo 'Build Successful'
        }
        failure {
            echo 'Build Failed'
        }
    }
}
