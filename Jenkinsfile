@Library('anil_shared_lib') _

pipeline {
    agent any    
    tools{
        maven "Maven-3.9.6"
    }
    stages {
        stage('Clone') {
            steps {
             git branch: 'main', credentialsId: 'GIT-CREDENTIALS', url: 'https://github.com/anilchavan123/courses_web_app.git'
            }
        }
        stage('Maven Build'){
            steps{
              mavenBuild()
            }
        }
		stage('Code Review'){
			steps{
				sonarQube()
			}
		}
    }
}
