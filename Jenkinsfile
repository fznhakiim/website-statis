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
                    echo 'Memulai deployment...'
                    if (isUnix()) {
                        sh '''
                        # Membuat direktori tujuan jika belum ada
                        sudo mkdir -p /var/www/html/website-statis
                        # Menyalin seluruh file ke direktori tujuan
                        sudo cp -r * /var/www/html/website-statis/
                        '''
                    } else {
                        bat '''
                        REM Membuat direktori tujuan jika belum ada
                        if not exist "C:\\var\\www\\html\\website-statis" mkdir "C:\\var\\www\\html\\website-statis"
                        REM Menyalin seluruh file ke direktori tujuan
                        xcopy * "C:\\var\\www\\html\\website-statis\\" /E /I /Y
                        '''
                    }
                    echo 'Deployment berhasil!'
                }
            }
        }
    }
}
