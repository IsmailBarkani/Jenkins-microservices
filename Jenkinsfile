// pipline declarative syntaxes
pipeline{
	agent any
	//agent{docker {image 'maven:3.6.3'} }

	environement{
		dockerHome = tool 'myDocker'
		mavenHome = tool 'myMaven'
		PATH = "$dockerHome/bin:$mavenHome/bin:$PATH"
	}
	stages{
		stage('Build'){
			steps{
				sh 'mvn --version'
				sh 'docker version'
				echo 'Build'
				echo  "Path - $PATH"
				echo  "Build number - $env.BUILD_NUMBER"
				echo  "Build id - $env.BUILD_ID"
				echo  "JOB name - $env.JOB_NAME"
				echo  "Build TAGE - $env.BUILD_TAG"
				echo  "Build url - $env.BUILD_URL"
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