pipeline {
    agent any

    stages {
        stage('Clone Repo') {
            steps {
                git 'https://github.com/<username>/flask-backend.git'
            }
        }

        stage('Install Dependencies') {
            steps {
                sh 'pip3 install -r requirements.txt'
            }
        }

        stage('Restart Flask') {
            steps {
                sh 'pm2 restart flask-backend || pm2 start app.py --name flask-backend --interpreter python3'
            }
        }
    }
}
