pipeline {
    agent any

    tools {
        nodejs 'NodeJS 23.11.0'
    }

    stages {
        stage('Clone Code') {
            steps {
                git 'https://github.com/whoschetna/SimpleNodeApp.git'
            }
        }

        stage('Install Dependencies') {
            steps {
                sh 'npm install'
            }
        }

        stage('Run Application') {
            steps {
                sh 'nohup npm start > output.log 2>&1 &'
                echo 'App started in the background!'
            }
        }
    }
}
