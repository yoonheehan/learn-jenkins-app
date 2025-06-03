pipeline {
    agent any

    stages {
        stage('Build') {
            agent {
                docker {
                    image 'node:18-alpine'
                    reuseNode true
                }
            }
            steps {
                sh '''
                    ls -la
                    node --version
                    npm --version
                    # ci용 npm 설치
                    npm ci
                    npm run build
                    ls -la
                '''
            }
        }
    }
}