pipeline {
    agent any

    stages {
        stage('Clone Repo') {
            steps {
                echo 'Mengambil dari GitHub'
            }
        }

        stage('Deploy ke VPS') {
            steps {
                echo 'Menyalin ke /var/www/html'
                sh '''
                    sudo rm -rf /var/www/html/*
                    sudo cp -r * /var/www/html/
                '''
            }
        }
    }
}
