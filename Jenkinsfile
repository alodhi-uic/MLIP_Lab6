pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Setup Python Environment') {
            steps {
                sh '''
                    python3 -m venv mlip
                    source mlip/bin/activate
                    pip install pytest numpy pandas scikit-learn
                '''
            }
        }

        stage('Run Tests') {
            steps {
                sh '''
                    source mlip/bin/activate
                    pytest
                '''
            }
        }
    }
}
