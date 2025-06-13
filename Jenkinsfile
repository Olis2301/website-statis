pipeline {
    agent any

    stages {
        stage('Clone Repo') {
            steps {
                git branch: 'main', url: 'https://github.com/Olis2301/website-statis.git'
            }
        }

        stage('Deploy to VPS') {
            steps {
                sh '''
                    scp -o StrictHostKeyChecking=no -r 404.html 500.html Jenkinsfile README.md css img index.html js root@202.10.41.102:/var/www/html/
                '''
            }
        }
    }
}