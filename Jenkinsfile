pipeline {
	agent any
	environment {
		filename_environment = 'fichier_environment.txt'
	}
	parameters {
		string name: 'filename_parameters', description: 'File to download', defaultValue: 'fichier_parameters.txt'
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
				echo "File to download environment : ${filename_environment}"
				echo "File to download parameters : ${params.filename_parameters}"
				echo "FileName_userText = ${userText}"
				sh "echo FileName_userText = ${userText}"

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
