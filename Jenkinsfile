//Assignment 10
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
	withCredentials([[$class: 'AmazonWebServicesCredentialsBinding', accessKeyVariable: 'AWS_ACCESS_KEY_ID', credentialsId: '23f267e5-41c2-4622-b807-aaf5cc7dc4fe', secretKeyVariable: 'AWS_SECRET_ACCESS_KEY']]) {
    		sh 'aws cloudformation describe-stack-resources --region us-east-1 --stack-name jenkins'
		}
	junit 'reports/result.xml'
	}
}
