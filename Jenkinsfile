properties([pipelineTriggers([githubPush()])])
node('linux') {
    git credentialsId: 'github-credential', url: 'https://github.com/buhr3940/java-project.git'
    stage('Test') {
        sh 'ant -f test.xml -v'
    }
    stage ('Build') {
        sh 'ant -f build.xml -v'
    }
    stage ('Deploy') {
	sh 'aws s3 cp http://52.207.242.13:8080/workspace/java-pipeline/*.jar s3://buhr3940-pipeline-bucket/index.html'
    }
    stage ('Report') {
        junit 'reports/result.xml'   
    }
}
