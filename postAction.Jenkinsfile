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
            script {
                def addedFiles = sh(script: 'git diff --diff-filter=A --name-only HEAD~1 HEAD^', returnStdout: true).trim()
                def commitHash = sh(script: 'git rev-parse HEAD', returnStdout: true).trim()
                def previousCommitHash = sh(script: 'git rev-parse HEAD~1', returnStdout: true).trim()
                echo "New files added: ${addedFiles}"
                echo "Commit hash: ${commitHash}"
                echo "Previous commit hash: ${previousCommitHash}"
                if (addedFiles) {
                    echo "New files added: ${addedFiles}"
                } else {
                    echo 'No new files added'
                }
                echo 'This will run only if successful'
            }
        }
        always {
            echo 'This will always run'
        }
    }
}
