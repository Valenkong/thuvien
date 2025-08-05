pipeline {
    agent any

    environment {
        // Biến môi trường nếu cần
        GIT_BRANCH = "main"
    }

    stages {
        stage('Checkout') {
            steps {
                // Lấy mã nguồn từ nhánh chỉ định
                git branch: "${GIT_BRANCH}", url: 'https://github.com/Valenkong/thuvien.git'
            }
        }

        stage('Build') {
            steps {
                echo 'Đang build project...'
                // Ví dụ: build bằng Maven
                sh 'mvn clean install'
            }
        }

        stage('Test') {
            steps {
                echo 'Đang chạy test...'
                sh 'mvn test'
            }
        }

        stage('Deploy') {
            when {
                branch 'main'
            }
            steps {
                echo 'Triển khai ứng dụng...'
                // Triển khai nếu cần
            }
        }
    }

    post {
        success {
            echo 'Build thành công!'
        }
        failure {
            echo 'Build thất bại.'
        }
    }
}
