pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building...'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying website...'
                // contoh: copy file ke /var/www/html (jika Jenkins di server lokal)
                // sh 'cp -r * /var/www/html/'
            }
        }
    }
}
