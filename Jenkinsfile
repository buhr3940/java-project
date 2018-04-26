properties([pipelineTriggers([githubPush()])])
node('linux') {
    stage('Test') {
        git url: 'https://github.com/buhr3940/java-project.git', branch: 'master'
        sh 'ant -f test.xml -v'
    }
    stage ('Build') {
        sh 'ant'
    }
}
