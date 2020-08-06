pipeline {
    agent any
	
   environment {
        HOME = '/var/lib/jenkins'
        NVM_DIR='/var/lib/jenkins/.nvm'
    }
    stages {
        stage('Start') {
            steps {
        echo 'Install nvm ${env.HOME} ${env.NVM_DIR}'
		sh 'wget -qO- https://raw.githubusercontent.com/nvm-sh/nvm/v0.35.3/install.sh | bash'
		echo 'checking nvm'			
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
