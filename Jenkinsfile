pipeline {
    agent {
        node {
            label 'Agent-1'
        }
    }
    environment {
        COURSE = "jenkins"
    }
    stages {
        stage('Build') {
            steps {
                echo "buliding"    
            }
        }
        stage('Test') {
            steps {
                script {
                   sh """
                      echo "testing"
                      echo $COURSE
                    """ 
                }
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

