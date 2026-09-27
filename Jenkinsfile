pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Docker Check') {
            steps {
                sh 'docker --version'
            }
        }

        stage('ERPNext Image Check') {
            steps {
                sh 'docker pull frappe/erpnext:version-16'
            }
        }
    }

    post {
        success {
            echo 'ERPNext Jenkins pipeline completed successfully!'
        }
        failure {
            echo 'Jenkins pipeline failed.'
        }
    }
}
