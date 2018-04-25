properties([pipelineTriggers([githubPush()])])

node('linux') {   
	stage('Test') {    
		git credentialsId: 'github-credential', url: 'https://github.com/buhr3940/java-project.git'
		sh 'ant -buildfile test.xml'   
	}   
	stage('Build') {    
		sh 'ant'   
	}   
	stage('Results') {    
		junit 'reports/*.xml'   
	}
}
