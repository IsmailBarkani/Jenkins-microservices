//Pipeline declarative
pipeline {
	//agent{docker {image 'maven:3.6.3'}}
	agent any
	stages{
		stage('Build'){
			steps{
				//sh 'mvn --version'
				echo "Build"
				echo "Buil number = $env.BUILD_NUMBER"
				echo "Buil identification = $env.BUILD_ID"
				echo "Build url = $env.BUILD_URL"
				echo "Job Name = $env.JOB_NAME"
				echo "$PATH"
			}
		}

		stage('Test'){
			steps{
				echo 'Test'
			}
		}

		stage('Integration Test'){
			steps{
				echo "Integration Test"
			}
		}
	}

	post{
		always{
			echo "Always run this"
		}
		success{
			echo "run the API"
		}
		failure{
			echo "Clean"
		}

	}
}