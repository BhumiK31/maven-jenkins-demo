pipeline {
    agent {
        docker {
            image 'maven:3.9.6-eclipse-temurin-17'
            args '-v /root/.m2:/root/.m2'
        }
    }

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
            echo '✅ Build completed successfully!'
        }
        failure {
            echo '❌ Something went wrong in the pipeline.'
        }
    }
}
