pipeline {
		agent any
		//agent{ docker { image 'node:18.9'}}
		stages {
			stage('Build'){
				steps{
					sh 'mvn --version'
					sh 'docker version'
					echo "Build"
					echo "PATH - $PATH"
					echo "BULID_NUMBER - $env.BULID_NUMBER"
					echo "BULID_ID - $env.BULID_ID"
					echo "JOB_NAME - $env.JOB_NAME"
					echo "BUILD_URL - $env.BUILD_URL"
					echo "BUILD_TAG - $env.BUILD_TAG"
				}
			}
			stage('Test'){
				steps{
					echo "Test"
				}
			}
			stage('Integration Test'){
				steps{
					echo "Integration Test"
				}
			}
		} 
		
		post{
			always {
				echo 'mr blow runs me'
			}
			success {
				echo 'mr blow made me successful'
			}
			failure {
				echo 'I disobeyed mr blow'
			}
		}
}