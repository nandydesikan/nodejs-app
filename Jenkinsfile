pipeline {
    agent any
	
   environment {
        
        NVM_DIR='/var/lib/jenkins/.nvm'
    }
    stages {
        stage('Start') {
            steps {
				sh 'echo  ${NVM_DIR}'
				nodejs(nodeJSInstallationName: 'Node 6.x', configId: '<config-file-provider-id>') {
                    sh 'npm config ls'
                }
		
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
