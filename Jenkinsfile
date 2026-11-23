pipeline {
    agent any

    triggers {
        pollSCM('H/2 * * * *')
    }

    stages {
        stage('Show commit') {
            steps {
                sh 'git log -1 --oneline'
            }
        }
        stage('Check project files') {
            steps {
                sh 'test -f Dockerfile'
                sh 'test -f app.py'
                sh 'test -f requirements.txt'
                echo 'All required files are present'
            }
        }
    }
}