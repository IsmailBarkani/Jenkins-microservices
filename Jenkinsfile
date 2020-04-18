// pipline declarative syntaxes
pipeline{
	agent any
	//agent{docker {image 'maven:3.6.3'} }

	environment{
		dockerHome = tool 'myDocker'
		mavenHome = tool 'myMaven'
		PATH = "$dockerHome/bin:$PATH"
	}
	stages{
		//CheckOut stage
		stage('CheckOut'){
			steps{
				withMaven(maven : 'myMaven') {
						bat 'mvn --version'
				}
				//bat 'mvn --version'
				bat 'docker version'
				echo 'Build'
				echo  "Path - $PATH"
				echo  "Build number - $env.BUILD_NUMBER"
				echo  "Build id - $env.BUILD_ID"
				echo  "JOB name - $env.JOB_NAME"
				echo  "Build TAGE - $env.BUILD_TAG"
				echo  "Build url - $env.BUILD_URL"
			}
		}

		//Compile Stage
		stage('Compile'){
			steps{
				withMaven(maven: 'myMaven'){
					bat 'mvn compile'
				}
			}
		}
		//Integration test stage
		stage('Integration Test'){
			steps{
				withMaven(maven: 'myMaven'){
					bat 'mvn failsafe:integration-test failsafe:verify'
				}
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