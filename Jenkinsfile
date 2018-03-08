pipeline {
    agent any 
    stages {
        stage('Checkout SCM') { 
            steps {
              checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[url: 'https://github.com/jibinjose087/ansiblePlaybookSample.git']]])
            }
        }
        stage('Ansible') { 
            steps {
            ansiblePlaybook credentialsId: '14b010f2-3bce-416b-96e3-dd889ff4f0f6', extras: '"test1":"JIBIN", "test2":"TOM"', inventory: '${WORKSPACE}/environments/dev.ini', playbook: '${WORKSPACE}/site.yml', sudoUser: null
            }
        }
        stage('Deploy') { 
            steps {
                sh "echo 'deployment completed'"
            }
        }
    }
}
