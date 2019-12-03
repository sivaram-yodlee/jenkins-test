pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh 'echo "Blue ocean auto trigger"'
                sh '''
                    echo "Multiline shell steps works too"
                    ls -lah
                '''
            }
        }
    }
}