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
        stage('Sonarqube') {
            environment {
                scannerHome = tool 'SonarQubeScanner'
            }

            steps {
                withSonarQubeEnv('SonarServer') {
                    sh "${scannerHome}/bin/sonar-scanner"
                }
                timeout(time: 10, unit: 'MINUTES') {
                    waitForQualityGate abortPipeline: true
                }   
            }
        }   
    }
}