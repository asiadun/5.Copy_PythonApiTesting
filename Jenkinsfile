pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing'
                py.test --alluredir=allure-results -s -q
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying'
            }
        }
    }
}