pipeline {
    agent none
    stages {
	    stage('Clone repository'){
			steps {
       			 git 'https://github.com/bhavika1/SpringBootDockerJenkins.git'
      		}
		}
        stage('Build image'){
        	steps{
        		script{
        			docker.build bhavikapande/springbootnew + ":1"
        		}
        	}
		}
		stage('Push Image'){
			steps{
				script{
					docker.withRegistry('https://registry.hub.docker.com','docker-hub'){
						dockerImage.push()
					}
				}
			}
		}
	}
}