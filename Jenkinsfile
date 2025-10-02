pipeline {
    agent { 
		label '1C_test'
	}
	
	environment {
		repo = ''
    }
	
    stages {
        stage('Build') {
            steps {
				bat "chcp 65001\n vrunner init-dev"
            }
        }
        stage('Syntax check') {
            steps {
                bat "chcp 65001\n vrunner syntax-check"
			}
        }
        stage('Smoke tests') {
            steps {
                bat "chcp 65001\n vrunner xunit"
            }
        }
    }
	
	post {
        always {
			allure includeProperties: false, jdk: '', results: [[path: 'ut/syntax-check/allure']]
            junit stdioRetention: 'ALL', testResults: 'out/syntax-check/junit/*.xml'
        }
        failure {			
			emailext body: 'The Pipeline failed :(',
			subject: 'Jenkins',
			to: 'akim_rabota@mail.ru'
        }
	}
}