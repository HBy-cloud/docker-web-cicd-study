pipeline {
    agent any

    stages {
        stage('1. Check Files') {
            steps {
                sh 'ls -la'
            }
        }
        stage('2. Test index.html') {
            steps {
                sh 'grep -q "Hello from my Docker Container!" index.html'
                echo 'index.html 테스트 통과!'
            }
        }
        stage('3. Check Dockerfile') {
            steps {
                sh 'grep -q "FROM nginx:alpine" Dockerfile'
                sh 'grep -q "COPY index.html /usr/share/nginx/html/index.html" Dockerfile'
                echo 'Dockerfile 검증 통과!'
            }
        }
    }
}