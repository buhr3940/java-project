properties([pipelineTriggers([githubPush()])])
node('java') {
    git url: 'https://github.com/buhr3940/java-projectd.git', branch: 'master'
    stage('Test') {
        sh "env"
    }
    stage('Build') {    
		sh 'ant'   
	}   
}
