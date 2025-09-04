pipeline {
	agent any
	stages {
		stage('Download') {
			steps {
				script {
					def userText = input(
						id: 'UserInput', message: 'File to download :',
						parameters: [
							string(defaultValue: 'fichier.txt', description: 'File to download', name: 'FileName')
						]
					)
				}
				echo "File to download : ${params.FileName}"
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
