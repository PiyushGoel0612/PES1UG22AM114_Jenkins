pipeline {
    agent any  // Runs on any available Jenkins agent

    stages {
        stage('Checkout Code') {
            steps {
                git branch: 'main', url: 'https://github.com/PiyushGoel0612/PES1UG22AM114_Jenkins.git'
            }
        }

        stage('Build') {
            steps {
                script {
                    echo 'Compiling hello.cpp...'
                    sh 'g++ -o hello_exec hello.cpp'
                }
            }
        }

        stage('Test') {
            steps {
                script {
                    echo 'Running tests...'
                    sh './hello_exec'  // Executes the compiled C++ program
                }
            }
        }
    }

    post {
        success {
            echo 'Pipeline executed successfully!'
        }
        failure {
            echo 'Pipeline failed!'
        }
    }
}
