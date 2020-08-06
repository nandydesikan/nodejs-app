pipeline {
    agent any
   
    stages {
        stage('Start') {
            steps {
                echo 'Starting the build'
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


