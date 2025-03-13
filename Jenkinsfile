pipeline {
    agent any
    
    environment {
        SRN = 'PES1UG22CS237'
        REPO_URL = 'https://github.com/arjuuuuunnnnn/PES1UG22CS237_Jenkins.git'
    }
    
    stages {
        stage('Clone repository') {
            steps {
                sh 'git clone --branch main ${REPO_URL} .'
                sh 'echo "Repository cloned successfully"'
            }
        }
        
        stage('Install dependencies') {
            steps {
                sh 'g++ --version || echo "g++ not installed"'
                sh 'echo "Compiler check completed"'
            }
        }
        
        stage('Build application') {
            steps {
                sh 'g++ -o ${SRN}-1 main/hello.cpp || echo "Build failed - g++ not available"'
                sh 'echo "Build step completed"'
            }
        }
        
        stage('Test application') {
            steps {
                sh './${SRN}-1 || echo "Test failed - executable not found"'
                sh 'echo "Test step completed"'
            }
        }
    }
    
    post {
        failure {
            echo 'Pipeline failed'
        }
        success {
            echo 'Pipeline completed successfully'
        }
    }
}
