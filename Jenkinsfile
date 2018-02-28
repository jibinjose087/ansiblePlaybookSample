pipeline {
    agent any
        parameters {
                booleanParam(defaultValue: true, description: '', name: 'testbool')
                string(defaultValue: Jibin, description: '', name: 'name')
            }

        stages {
            stage ('Git SCM stage'){
                steps {
                sh 'echo "Download Stage ${params.testbool}"'
                }
            }
            stage ('Build Stage'){
                steps {
                sh 'echo "The job ${params.name} going to start the Build Stage"'
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
