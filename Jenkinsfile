pipeline {
    agent any
	
	
   tools { nodejs "node" }	
   environment {
        
        NVM_DIR='/var/lib/jenkins/.nvm'
    }
    stages {
        stage('Start') {
            steps {
					sh 'echo  ${NVM_DIR}'				
                    sh 'npm config ls'
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
			echo 'Exporting variables'
			sh 'export HOME=${HOME}'
			sh 'export NVM_DIR=${NVM_DIR}'
	        sh 'chmod 777 -R *'            
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
