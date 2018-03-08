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
            ansiblePlaybook credentialsId: '14b010f2-3bce-416b-96e3-dd889ff4f0f6', extras: '-e test1="JIBIN", -e test2="TOM", -e test3="SUCCESS"'', inventory: '${WORKSPACE}/environments/dev.ini', playbook: '${WORKSPACE}/site.yml', sudoUser: null
            }
        }
        stage('Deploy') { 
            steps {
                sh "echo 'deployment completed'"
            }
        }
    }
}
