pipeline {
    agent {
        node {
            label 'Agent-1'
        }
    }
    environment {
        COURSE = "jenkins"
    }
    options {
        timeout(time :10, unit: 'SECONDS')
        disableConcurrentBuilds()
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
                      sleep 10
                      env
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
        aborted {
            echo "pipeline is aborted"
        }
    }
}

