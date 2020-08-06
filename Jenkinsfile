pipeline {
    agent any
	
   environment {
        
        NVM_DIR='/var/lib/jenkins/.nvm'
    }
    stages {
        stage('Start') {
            steps {
        sh 'echo  ${NVM_DIR}'
		sh 'wget -qO- https://raw.githubusercontent.com/nvm-sh/nvm/v0.35.3/install.sh | bash'
		echo 'Exporting variables'
		sh 'echo ${HOME}'
		sh 'export NVM_DIR=${NVM_DIR}'
		echo 'checking nvm'		
		sh 'bash /var/lib/jenkins/.nvm/nvm.sh'
		sh 'nvm --version || exit 1'
		sh 'nvm install node'
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
