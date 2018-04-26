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
	sh 'aws s3 cp $WORKSPACE/dist/*.jar s3://buhr3940-pipeline-bucket/index.html'
    }
    stage ('Report') {
        junit 'reports/result.xml'
	sh 'aws cloudformation describe-stack-resources --region us-east-1 --vpc vpc-e2df9199 --security-group-ids sg-fbfbabb2 --stack-name jenkins'    
    }
}
