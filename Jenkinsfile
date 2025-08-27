pipeline {
    agent any
    
    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/<your-username>/python-ci-pipeline.git'
            }
        }
        
        stage('Install Dependencies') {
            steps {
                sh 'pip3 install pytest'
            }
        }
        
        stage('Run Tests') {
            steps {
                sh 'pytest --maxfail=1 --disable-warnings -q'
            }
        }
    }
    
    post {
        always {
            junit '**/test-results.xml' allowEmptyResults: true
        }
    }
}
