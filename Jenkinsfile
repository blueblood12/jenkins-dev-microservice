pipeline {
		agent any
		stages {
			stage('Build'){
				steps{
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
		} post{
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