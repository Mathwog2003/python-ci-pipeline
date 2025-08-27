pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/gowtham/python-ci-pipeline.git'
            }
        }
        
        stage('Install Dependencies') {
            steps {
                sh 'pip3 install pytest'
            }
        }
        
        stage('Run Tests') {
            steps {
                sh 'pytest --junitxml=test-results.xml'
            }
        }
    }
    
}
