pipeline {
    agent {
        docker {
            image 'maven:3.8.8'
            args '-v /var/run/docker.sock:/var/run/docker.sock'
        }
    }
    stages {
        stage('Build') {
            steps {
                sh 'docker version'
                sh 'docker inspect -f . maven:3.8.8 || docker pull maven:3.8.8'
                sh 'mvn --version'
                echo 'Building...'
                // Your build steps here
            }
        }
        stage('Test') {
            steps {
                echo 'Testing...'
                // Your test steps here
            }
        }
        stage('Integration Test') {
            steps {
                echo 'Running Integration Tests...'
                // Your integration test steps here
            }
        }
    }
    post {
        always {
            echo 'I am awesome. I run always.'
        }
        success {
            echo 'I run when you are successful.'
        }
        failure {
            echo 'I run when you fail.'
        }
        unstable {
            echo 'I run when the build is unstable.'
        }
        changed {
            echo 'I run when the build status changes.'
        }
    }
}
