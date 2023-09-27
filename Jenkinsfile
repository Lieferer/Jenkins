pipeline {
    environment {
    //First variable
    doError = '0'
    }
    agent any
    triggers {
        pollSCM 'H/2 * * * *'
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
        stage('Failure') {
            when{
                expression { doError == '1' }
                }
            steps {
                echo 'Build was not successful'
                }
        }
        stage('Successful') {
            when{
                expression { doError == '0'}
            }
            steps {
                echo 'Build was successful!'
            }
            }
        }
    post {
        always {
            echo 'This is displayed always'
        }
        success {
            echo 'The Build has been completed'
            writeFile(file: "c:/temp/File.txt", text: "First created File")
        }
        failure {
            error 'The Build was a mess :-('
        }
        }
    }

