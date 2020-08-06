pipeline {
    agent any
   
    stages {
        stage('Build') {
            steps {
                echo 'Starting the build'
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
   
    post {
        
        }
    }
