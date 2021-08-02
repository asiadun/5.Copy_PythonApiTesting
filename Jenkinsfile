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
                sh 'py.test /test_allure.py --alluredir /tmp/allure-results'                
            }
        }
        stage('Deploy') {
            steps {
                sh 'py.test --alluredir=allure-results -s -q'
            }
        }
    }
}