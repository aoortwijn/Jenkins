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
    }
    post {
        always {
            echo 'Always'
        }
        success {
            echo 'Success'
        }
        failure{
            echo 'Failure'
        }
    }
}
