//Pipeline declarative
pipeline {
	agent any
	stages{
		stage('Build'){
			steps{
				echo "Build"
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