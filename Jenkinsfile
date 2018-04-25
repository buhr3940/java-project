properties([pipelineTriggers([githubPush()])])
node('java-project') {
    git url: 'https://github.com/buhr3940/java-project.git', branch: 'master'
    stage('Test') {
	    sh 'env'
    }

stage ('Build') {

    sh 'ant -f build.xml -v'

    }

}
