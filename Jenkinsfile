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
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}