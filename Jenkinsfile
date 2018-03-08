pipeline {
    agent any 
    deleteDir ()
    stages {
        stage('Checkout SCM') { 
            steps {
              checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[url: 'https://github.com/jibinjose087/ansiblePlaybookSample.git']]])
            }
        }
        stage('Test') { 
            steps {
              sh "echo 'hello world'"
            }
        }
        stage('Deploy') { 
            steps {
            currentBuild.result = 'FAILED'
            }
        }
    }
}
