pipeline {
    agent any
    stages {
        stage('Clone Repo') {
            steps {
                git 'https://github.com/username/php-app.git'
            }
        }
        stage('Install Dependencies') {
            steps {
                sh 'composer install'
            }
        }
        stage('Test') {
            steps {
                sh './vendor/bin/phpunit tests'
            }
        }
        stage('Build Docker Image') {
            steps {
                sh 'docker build -t php-app .'
            }
        }
        stage('Deploy') {
            steps {
                sh 'docker run -d -p 8081:80 php-app'
            }
        }
    }
}
