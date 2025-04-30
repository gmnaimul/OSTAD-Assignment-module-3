pipeline {
    agent any

    stages {
        stage('Clone') {
            steps {
                echo 'Cloning repository...'
                git branch: 'main', url: 'https://github.com/gmnaimul/OSTAD-Assignment-module-3.git'
            }
        }
        stage('Install') {
            steps {
                echo 'Installing dependencies...'
                sh 'npm install'
            }
        }
        stage('Test') {
            steps {
                echo 'Running tests...'
                sh 'npm run test:ci'
                
            }
        }
    }

    post {
        always {
        echo 'Build finished'
        junit 'test-results/results.xml'
                }
    success {
        echo 'Build succeeded!'
            }
    failure {
        echo 'Build failed!'
    }
}

}
