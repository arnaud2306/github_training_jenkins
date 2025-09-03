pipeline {
	agent any
	parameters {
		string(name:'File',defaultValue:"File_to_download.txt",description:"File to download")
	}	
	stages {
		stage('Download') {
			steps {
				sh "echo 'Stage Download ${params.File}'"
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
