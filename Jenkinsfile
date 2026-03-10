pipeline {
    agent {
        node {
            label 'Agent-1'
        }
    }
     
    stages {
        stage('Build') {
            steps {
                echo "buliding"
            }
        }
        stage('Test') {
            steps {
                echo "testing"
            }
        }
        stage('Deploy') {
            steps {
                echo "deploying"
            }
        }
    }
    post {
        always {
            echo "i will run if success or not"
            cleanWs()
        }
        success {
            echo "i will run if success"
        }
        failure {
            echo "i will run if failure"
        }
    }
}

