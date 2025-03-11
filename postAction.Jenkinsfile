pipeline {
    agent any
    stages {
        stage('compile') {
            steps {
                echo 'mvn clean compile'
            }
        }
        
    }

    post {
        success {
            echo 'This will run only if successful'
        }
        always {
            echo 'This will always run'
        }
    }
}
