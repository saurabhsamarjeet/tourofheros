pipeline {
	agent any 
	stages{
	    stage('checkout the code'){
	        steps {
	                    cleanWs()
                      checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/saurabhsamarjeet/tourofheros.git']]])
                           
                     }
              }
	    stage ('Build and Push') {
		      steps {
			          bat ' docker build -t tourofheros .'
		      }
	    }
	    stage ( 'Run the docker') {
		      steps {
			          bat ' docker run -d -p 4200:4200 tourofheros '
		      }
	    }
  }
}
