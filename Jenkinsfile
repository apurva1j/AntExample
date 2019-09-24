pipeline {
    agent any 
	environment
	{
	ant_options_theme_private = "C:\\Apurva\\JenkinsWorkspace\\build.xml "
	}
    stages {
        stage('Git Checkout') { 
            steps {
                checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[url: 'https://github.com/apurva1j/AntExample.git']]])
            }
        }
        stage('Test') { 
            steps {
                bat "echo Test"
            }
        }
		stage('Build') {
		steps
		{
		withAnt(installation: 'Ant 1.10.7', jdk: 'jdk-11.0.4') {
		// some block
		bat "${ant_options_theme_private}"
		}
}
		}
		
        stage('Deploy') { 
            steps {
                bat "echo Deploy"
            }
        }
    }
	
}

