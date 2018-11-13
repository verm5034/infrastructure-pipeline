properties([pipelineTriggers([githubPush()])])
node('linux') {
    git url: 'https://github.com/verm5034/infrastructure-pipeline.git', branch: 'master'
    stage('Test') {
        sh "env"
    }
}
