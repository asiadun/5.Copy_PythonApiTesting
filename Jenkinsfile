pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                bat 'pip install -r requirements.txt'
            }
        }
        stage('Deploy') {
            steps {
                bat 'py.test --alluredir=allure-results -s -q || true'
            }
        }
        stage('Deploy_allure') {
            steps {
                script {
                    allure([
                        includeProperties: false,
                        jdk: '',
                        properties: [],
                        reportBuildPolicy: 'ALWAYS',
                        results: [[path: 'allure-results']]
                    ])
                }
            }   
        }
    }
}