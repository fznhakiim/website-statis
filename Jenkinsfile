pipeline {
    agent any
    stages {
        stage('Clone Repository') {
            steps {
                // Clone kode dari repository GitHub
                git 'https://github.com/fznhakiim/website-statis.git'
            }
        }
        stage('Build & Test') {
            steps {
                // Untuk HTML statis, tidak ada proses build/test
                echo 'Tidak ada pengujian yang diperlukan untuk HTML statis'
            }
        }
        stage('Deploy to Server') {
            steps {
                // Deployment ke server staging (contoh: direktori lokal web server)
                sh '''
                mkdir -p /var/www/html/website-statis
                cp -r * /var/www/html/website-statis
                '''
                echo 'Deployment berhasil!'
            }
        }
    }
}
