pipeline {
    agent any

    environment {
        VENV = "venv"
    }

    stages {
        stage('Clone GitHub Repo') {
            steps {
                git branch: 'main', credentialsId: 'github-https', url: 'https://github.com/viksh20/Pipelining_pythonApp'
            }
        }

        stage('Set Up Python Virtual Environment') {
            steps {
                bat '"C:\Users\happy\AppData\Local\Microsoft\WindowsApps\python.exe" -m venv venv'
                bat '.\\venv\\Scripts\\python.exe -m pip install --upgrade pip'
                bat '.\\venv\\Scripts\\pip install numpy flask pandas tensorflow'
            }
        }

        stage('Run Flask App') {
            steps {
                bat '.\\venv\\Scripts\\python app.py'
            }
        }
    }
}
