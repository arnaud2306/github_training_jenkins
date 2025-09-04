pipeline {
	agent any
	environment {
		FileName = 'fichier_environment.txt'
	}
	parameters {
		string name: 'FILENAME', description: 'File to download', defaultValue: 'fichier_parameters.txt'
	}
	stages {
		stage('Download') {
			steps {
				script {
					def userText = input(
						id: 'UserInput', message: 'File to download :',
						parameters: [
							string(defaultValue: 'fichier.txt', description: 'File to download', name: 'FileName_userText')
						]
					)
				}
				echo "File to download environment : ${FileName}"
				echo "File to download parameters : ${FILENAME}"
				input 'Continue to next stage ?'
			}
		}

		stage('Compile') {
			steps {
				sh 'echo "Stage Compile"'
			}
		}
	}
}
