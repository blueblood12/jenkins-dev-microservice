pipeline {
		agent any
		//agent{ docker { image 'maven:3.6.3'}}

		environment {
			mavenHome = tool 'MyMaven'
			dockerHome = tool 'MyDocker'
			 PATH="$dockerHome/bin:$mavenHome/bin:$PATH"
		}
		
		stages {
			stage('checkout'){
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

			stage ('compile') {
				steps{
					sh "mvn clean compile"
				}
			}
		

			stage('Test'){
				steps{
					sh "mvn test"
				}
			}

			stage('Integration Test'){
				steps{
					sh "mvn failsafe:integration-test failsafe:verify"
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