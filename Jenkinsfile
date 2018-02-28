pipeline {
    agent any
        parameters {
            booleanParam(defaultValue: true, description: '', name: 'testbool')
            }
        stages {
            stage ('Git SCM stage'){
                steps {

                 echo "Jibin: ${params.testbool}"
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
                build 'ssansible-project'
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
