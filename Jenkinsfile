properties([pipelineTriggers([githubPush()])])
node('linux') {
    git url: 'https://github.com/buhr3940/java-project.git', branch: 'master'
    stage('Test') {
        sh "env"
    }
