pipeline {
    agent any

    environment {
        // Đặt các biến môi trường nếu cần
        MY_ENV_VAR = 'value'
    }

    stages {
        // Stage 1: Checkout Code
        stage('Checkout') {
            steps {
                // Lấy mã nguồn từ Git repository
                git 'https://github.com/your/repository.git'
            }
        }

        // Stage 2: Build
        stage('Build') {
            steps {
                script {
                    // Build project (Ví dụ: sử dụng Maven hoặc Gradle)
                    echo 'Building the project...'
                    sh 'mvn clean install'  // Maven build command
                }
            }
        }

        // Stage 3: Test
        stage('Test') {
            steps {
                script {
                    // Run unit tests
                    echo 'Running tests...'
                    sh 'mvn test'  // Maven test command
                }
            }
        }

        // Stage 4: Deploy
        stage('Deploy') {
            steps {
                script {
                    // Deploy project (Ví dụ: đưa lên server, AWS, etc.)
                    echo 'Deploying application...'
                    sh 'scp target/my-app.jar user@server:/path/to/deploy'
                }
            }
        }
    }

    post {
        always {
            // Cleanup actions (Ví dụ: dọn dẹp thư mục build, test report)
            echo 'Cleaning up...'
        }
        success {
            // Gửi thông báo khi thành công
            echo 'Build and deployment successful!'
        }
        failure {
            // Gửi thông báo khi thất bại
            echo 'Build or deployment failed!'
        }
    }
}
