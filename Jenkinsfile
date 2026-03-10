pipeline {
    // this is pre-build section
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
    parameters {
        string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
        text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')
        booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')
        choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')
        password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
    }
    // this is build section
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
                      echo "Hello ${params.PERSON}"

                      echo "Biography: ${params.BIOGRAPHY}"

                      echo "Toggle: ${params.TOGGLE}"

                      echo "Choice: ${params.CHOICE}"

                      echo "Password: ${params.PASSWORD}"
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

