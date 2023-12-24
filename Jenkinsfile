pipeline {
	agent any 
	stages{
	    stage('checkout the code'){
	        steps {
	                    cleanWs()
                         checkout([$class: 'GitSCM', branches: [[name: '*/master']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/saurabhsamarjeet/tourofheros.git']]])
                           
                     }
              }
	     Stage ('Build and Push') {
		steps {
			bash ' docker build -t tourofheros .'
		}
	}
	     Stage ( 'Run the docker')
		steps {
			bash ' docker run -d -p 4200:4200 tourofheros '
		}
	}
}
}