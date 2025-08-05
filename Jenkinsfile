pipeline {
    agent any

    environment {
        GIT_BRANCH = "main"
    }

    stages {
        stage('Checkout') {
            steps {
                git branch: "${GIT_BRANCH}", url: 'https://github.com/Valenkong/thuvien.git'
            }
        }

        stage('Test') {
            steps {
                echo 'Chạy test PHP nếu có'
                // Ví dụ: chạy PHPUnit nếu bạn có thiết lập
                // bat 'phpunit --configuration phpunit.xml'
            }
        }

        stage('SonarQube Analysis') {
            steps {
                echo 'Chạy SonarQube Scanner cho PHP'
                // Ví dụ: nếu bạn có Sonar Scanner CLI cài đặt
                // bat 'sonar-scanner -Dsonar.projectKey=thuvien -Dsonar.sources=.'
            }
        }

        stage('Deploy') {
            when {
                branch 'main'
            }
            steps {
                echo 'Triển khai ứng dụng'
                // Thêm bước deploy nếu cần
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
