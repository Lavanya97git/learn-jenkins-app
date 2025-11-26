pipeline {
    agent any

    stages {
        stage('build') {
            agent {
                docker {
                    image 'node:18-alpine'
                    reuseNode true
                }
            }   
            steps {
                sh '''
                    echo "building the app"
                    ls -la
                    node --version
                    npm --version
                    npm ci
                    npm run build
                    ls -la
                    npm test
                    echo a
                '''
            }
        }
        stage('test') {
            agent {
                docker {
                    image 'node:18-alpine'
                    reuseNode true
                }
            }
            steps {
                sh '''
                    find . -name "index.html
                    npm test
                    echo a
                '''
            }
        }
    }
}
