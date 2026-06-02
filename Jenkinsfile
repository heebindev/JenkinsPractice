pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                echo 'Checkout completed'
            }
        }

        stage('Build') {
            steps {
                echo 'Build completed successfully'
            }
        }

        stage('Test') {
            steps {
                echo 'Test completed successfully'
            }
        }
    }

    post {
        success {
            sh '''
                echo "Build Success" > build-result.txt
                echo "Jenkins build completed successfully." >> build-result.txt
                echo "Repository: JenkinsPractice" >> build-result.txt
            '''
            archiveArtifacts artifacts: 'build-result.txt', fingerprint: true
        }

        failure {
            echo 'Build failed!'
        }
    }
}