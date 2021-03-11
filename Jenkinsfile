pipeline {
    agent any
    stages {
        stage('Test') {
            steps {
                echo 'Placeholder'
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
