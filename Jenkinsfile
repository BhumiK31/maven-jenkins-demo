pipeline {
    agent any

    stages {
        stage('Compile') {
            steps {
                echo 'Compiling the code...'
                sh 'mvn compile'
            }
        }

        stage('Build') {
            steps {
                echo 'Building the project...'
                sh 'mvn package'
            }
        }

        stage('Test') {
            steps {
                echo 'Running tests...'
                sh 'mvn test'
            }
        }
    }

    post {
        success {
            echo '✅ Build and Test stages completed successfully!'
        }
        failure {
            echo '❌ Something went wrong in the pipeline.'
        }
    }
}
