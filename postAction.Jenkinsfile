pipeline {
    agent { docker { image 'maven:3.3.3' } }
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
