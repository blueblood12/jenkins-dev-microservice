pipeline {
		agent any
		//agent{ docker { image 'node:18.9'}}

		environment {
			dockerHome = tool 'MyDocker'
			mavenHome = tools 'MyMaven'
			PATH = "$dockerHome/bin:$mavenHome/bin:$PATH"
		}
		stages {
			stage('Build'){
				steps{
					//sh 'node --version'
					echo "Build"
					echo "$PATH"
					echo "BULID_NUMBER - $env.BULID_NUMBER"
					echo "BULID_ID - $env.BULID_ID"
					echo "TAG_TIMESTAMP - $env.TAG_TIMESTAMP"
					echo "JOB_BASE_NAME - $env.JOB_BASE_NAME"
					echo "EXECUTOR_NUMBER - $env.EXECUTOR_NUMBER"
					echo "BUILD_URL - $env.BUILD_URL"
					echo "JENKINS_URL - $env.JENKINS_URL"
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