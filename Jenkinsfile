pipeline {
    agent any
    stages {
        stage('Clone Repository') {
            steps {
                // Clone kode dari repository GitHub dengan branch main
                git branch: 'main', url: 'https://github.com/fznhakiim/website-statis.git'
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
                script {
                    // Pastikan Anda memiliki izin untuk menulis ke /var/www/html
                    echo 'Memulai deployment...'
                    sh '''
                    # Membuat direktori tujuan jika belum ada
                    sudo mkdir -p /var/www/html/website-statis
                    # Menyalin seluruh file ke direktori tujuan
                    sudo cp -r * /var/www/html/website-statis/
                    '''
                    echo 'Deployment berhasil!'
                }
            }
        }
    }
}
