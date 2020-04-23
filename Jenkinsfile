pipeline {
    agent none
    stages {
	    stage('Clone repository'){
			checkout scm
		}
        stage('Build image'){
			app = docker.build("bhavikapande/springbootnew")
		}
        stage('Test image'){
			echo "Done"
		}
		stage('Push Image'){
			docker.withRegistry('https://registry.hub.docker.com','docker-hub'){
				app.push("1")
			}
			echo "Pushing build to docker hub"
		}
    }
}