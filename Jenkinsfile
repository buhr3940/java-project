properties([pipelineTriggers([githubPush()])])

node('linux') {   
	stage('Test') {    
		sh 'ant -buildfile test.xml'   
	}   
	stage('Build') {    
		sh 'ant'   
	}   
}
