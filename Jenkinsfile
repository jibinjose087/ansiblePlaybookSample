pipeline {
    agent any
        parameters {
            booleanParam(defaultValue: Jibin, description: '', name: 'testbool')
            }
        stages {
            stage ('Git SCM stage'){
                steps {
                    sh "mkdir -p output"
                    writeFile file: "output/usefulfile.txt", text: "This file is useful, need to archive it."
                    writeFile file: "output/readme.md", text: "readme file"
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
