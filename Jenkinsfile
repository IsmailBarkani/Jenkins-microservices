// pipline declarative syntaxes
pipeline{
	agent any
	stages{
		stage('Build'){
			steps{
				echo 'Build'
			}
		}

		stage('Unit Test'){
			steps{
				echo 'Unit Test'
			}
		}

		stage('Integration Test'){
			steps{
				echo 'Integration Test'
			}
		}
	} 
	post {
		always {
			echo 'The service is running'
		}
		success {
			echo 'The service is running: Success'
		}
		failure {
			echo 'The service is running: Failure'
		}
	}
}