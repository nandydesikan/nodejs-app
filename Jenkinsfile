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
                sh 'git clone https://github.com/nandydesikan/nodejs-app.git'
            }
        }
        stage('Integration') {
            steps {
                sh 'integrate_test.sh'
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
