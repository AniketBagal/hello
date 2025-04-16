pipeline {
    agent any

    stages {
        stage('Clone Repository') {
            steps {
                git 'https://github.com/AniketBagal/hello.git'
            }
        }

        stage('Build .cpp File') {
            steps {
                bat 'g++ hello.cpp -o hello.exe'
            }
        }

        stage('Run Executable') {
            steps {
                bat '.\\hello.exe'
            }
        }
    }

    post {
        always {
            emailext body: 'Build finished. Check results.',
                     subject: 'Build Notification: Hello Project',
                     to: 'aniketbagal12345@gmail.com'
        }
    }
}
