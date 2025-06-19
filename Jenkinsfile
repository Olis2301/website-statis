pipeline {
    agent any

    stages {
        stage('Clone Repo') {
            steps {
                git branch: 'main', url: 'https://github.com/Olis2301/website-statis.git'
            }
        }

        stage('Deploy to Staging') {
            steps {
                echo 'Deploying to STAGING...'
                sh '''
                    scp -o StrictHostKeyChecking=no -r 404.html 500.html Jenkinsfile README.md css img index.html js root@202.10.41.102:/var/www/html-staging/
                '''
            }
        }

        stage('Approval to Production') {
            steps {
                input message: 'Apakah kamu yakin ingin deploy ke PRODUCTION?'
            }
        }

        stage('Deploy to Production') {
            steps {
                echo 'Deploying to PRODUCTION...'
                sh '''
                    scp -o StrictHostKeyChecking=no -r 404.html 500.html Jenkinsfile README.md css img index.html js root@202.10.41.102:/var/www/html/
                '''
            }
        }
    }
}
