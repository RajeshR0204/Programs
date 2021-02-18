pipeline {
    agent { docker { image 'maven:3.3.3' } }
    stages {
        stage('One') {
                steps {
                        echo 'Hi, this is Rajesh from SRE Training'
			
                }
        }
	    stage('Two'){
		    
		steps {
			input('Do you want to proceed????')
        	}
	    }
        stage('Three') {
                when {
                        not {
                                branch "master"
                        }
                }
                steps {
			echo "Hello"
                }
        }
        stage('Four') {
                parallel {
                        stage('Unit Test') 
                        {
                                steps{
                                        echo "Running the unit test..."
					sh '''
                    				echo "Multiline shell steps works too"
                    				ls -lah
                			'''
                                }
                        }
                        stage('Integration Test') 
                        {
                                steps{
                                        sh 'mvn --version'
					echo "Running the int test..."
                                }
                        }
                }
        }
    }
}

