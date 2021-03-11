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
            mail to: 'amberoortwijn@gmail.com',
            subject: "Success Jenkins"
            body: "even testen toch"
        }
        failure{
            echo 'Failure'
        }
    }
}
