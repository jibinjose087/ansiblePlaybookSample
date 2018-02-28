pipeline {
    agent any
        parameters {
            booleanParam(defaultValue: Jibin, description: '', name: 'testbool')
            }
        stages {
            stage ('Git SCM stage'){
                when {
                    expression { params.testbool == 'Jibin' }
                }
                steps {
                    sh 'echo "Sucess with variable"'
                }
            }
            stage ('Build Stage'){
                steps {
                sh 'echo "The job going to start the Build Stage"'
                }
            }
            stage ('Deploy stage'){
                steps {
                retry(4) {
                sh 'echo "Deploy Stage multiple times"'
                        }
                }
            }
            stage ('artifact stage'){
                steps {
                sh 'echo "artifcat to artifactory"'
                }
            }
        }
        
    post {
        always {
        sh 'echo "deployment completed and the post build starts"'
            }
        changed {
        sh 'echo "ERROR in deployment"'
            }
    }
}
