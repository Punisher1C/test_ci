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
				bat "chcp65001\n vrunner init-dev --v8version 8.3.27.1688 --dt G:\\OTUS\\Jenkins\\1C_test\\template\\Test.dt --db-user Test --src F:\\OTUS\\jenCI\\src\\cf --ibconnection /FF:\\OTUS\\jenCI"
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