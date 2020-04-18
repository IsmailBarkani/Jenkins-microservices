// pipline declarative syntaxes
pipeline{
	agent{docker {image 'maven:3.6.3'} }
	stages{
		stage('Build'){
			steps{
				sh 'mvn --version'
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