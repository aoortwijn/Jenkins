pipeline {
    agent {
        label '!windows'
    }

    environment {
        ENV_1 = "Environment variable"
    }

    stages {
        stage('Test') {
            steps {
                echo 'Placeholder'               
            }
        }
        stage('Environment variable'){
            steps{
                echo "Environment ${ENV_1}"
                sh 'printenv'
            }
        }
        stage('No-op'){
            steps {
                sh 'ls'
            }
        }
        stage('Sanity check'){
            steps{
                input "input?"
            }
        }
        stage('Deploy - Staging'){
            steps{
                sh './deploy staging'
            }
        }
                
    }
    post {
        always {
            echo 'Always'
// kan locatie niet vinden, hoe werkt dat?
            // archiveArtifacts artifacts: 'build/libs/**/*.jar', fingerprint: true
            // junit 'build/reports/**/*.xml'
            deleteDir() 

        }
        success {
            echo 'Success'
        }
        failure{
            echo 'Failure'
        }
    }
}
