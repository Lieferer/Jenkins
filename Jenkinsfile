pipeline {
    agent any
    environment
    triggers {
        pollSCM 'H/2 * * * *'
    }
    when {

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
                echo "The build ID is ${env.BUILD_ID} and workspace path is ${env.WORKSPACE}"
            }
        }
    post {
        always {
          echo 'The Build has been completed'  
        }

    }
    }
}
