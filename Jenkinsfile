pipeline {
		//agent any
		agent{ docker { image 'node:18.9'}}
		stages {
			stage('Build'){
				steps{
					sh 'node --version'
					echo "Build"
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