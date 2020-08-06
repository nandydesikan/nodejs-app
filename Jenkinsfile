pipeline {
    agent {
		docker {
            image 'node:6-alpine'
            args '-p 3000:3000'
        }
	
	}
	environment {
        CI = 'true' 
    }
   
    stages {
        stage('Start') {
            steps {
					echo 'Install npm'		
					sh 'npm install'
            }
        }
	 stage('Build') {
            steps {
	       sh 'chmod 777 integrate_test.sh'
                sh 'git clone https://github.com/nandydesikan/nodejs-app.git'
            }
        }
        stage('Integration') {
            steps {
	        sh 'chmod 777 -R *'
                sh './node_modules/.bin/mocha ./test/test.js'
            }
        }
		stage ('Test Complete')
		{
			steps {
			echo 'Integration test complete'
			
			}
		
		}
    }  
   
    
}
