pipeline {

    agent any

        stages {

            stage ('Git Download Phase') { 
                steps { 
                   checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[url: 'https://github.com/jibinjose087/ansiblePlaybookSample.git']]])
                    sh 'echo "hellow download completed"'
                    }
                 }
            stage ('Play execuition Phase') {
                steps {
                sh 'echo "execuition started"'
                
                }
             }
            stage ('Build status') {
                steps {
                    script {
                        currentBuild.result = 'SUCCESS'
                     }
                
                }
            
            }
            
            }
        }
