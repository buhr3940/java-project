properties([pipelineTriggers([githubPush()])])
node('java-project-pipeline') {
    git url: 'https://github.com/buhr3940/java-project.git', branch: 'master'
    stage('Test') {
	    sh 'ant -f test.xml -v'
	    junit 'reports/result.xml'
    }

stage ('Build') {

    sh 'ant -f build.xml -v'

    }

}
