pipeline {
    agent any
        stages {
            stage ('Git SCM stage'){
                steps {
                sh 'echo "Download Stage"'
                }
            }
            stage ('Build Stage'){
                steps {
                sh 'echo "Build Stage"'
                }
            }
            stage ('Deploy stage'){
                steps {
                sh 'echo "Deploy Stage"'
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
