pipeline {
    agent any

    environment {
        NODE_HOME = tool name: 'NodeJS 23.11.0', type: 'NodeJS'
    }

    stages {
        stage('Clone Code') {
            steps {
                git 'https://github.com/whoschetna/SimpleNodeApp.git'
            }
        }

        stage('Install Dependencies') {
            steps {
                script {
                    sh 'npm install'
                }
            }
        }

        stage('Run Application') {
            steps {
                script {
                    sh 'nohup npm start > output.log 2>&1 &'
                    echo 'App started in the background!'
                }
            }
        }
    }

    post {
        always {
            echo 'Pipeline execution completed!'
        }

        success {
            echo 'Node.js app deployed successfully!'
        }

        failure {
            echo 'Pipeline failed!'
        }
    }
}
