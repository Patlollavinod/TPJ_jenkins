pipeline {
    agent any
    stages {
    stage('checkout '){
            steps{
                checkout([$class: 'GitSCM', branches: [[name: '*/feat-project2']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/prjpracticeteam/githubpractice.git']]])
            }
        }
        stage('docker image  build') {
            steps {
                sh 'docker build .'
            }
        }
        stage(' Runing python program'){
            steps{
               sh ' phython hashmap.py'
            }
        }
    }
}
