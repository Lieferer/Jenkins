pipeline {
    agent any
    triggers {
        pollSCM '*/2 * * * *'
    }
    stages {
        stage('Build') {
            steps {
                echo "Building.."
                
            }
        }
        stage('Test') {
            steps {
                echo "Testing.."
               
            }
        }
        stage('Deliver') {
            steps {
                echo 'Deliver....'
                echo 'The build ID is ${BUILD_ID} and workspace path is ${WORKSPACE}'
            }
        }
    }
}
