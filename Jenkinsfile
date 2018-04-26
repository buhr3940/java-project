properties([pipelineTriggers([githubPush()])])
node('linux') {
    git credentialsId: 'github-credential', url: 'https://github.com/buhr3940/java-project.git'
    stage('Test') {
	    sh 'ant -f test.xml -v'
    }

stage ('Build') {

    sh 'ant'

    }

}
