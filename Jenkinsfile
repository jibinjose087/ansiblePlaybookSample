pipeline {
    agent any
        stages {
            stage ('Git SCM stage'){
                steps {
                    sh "mkdir -p output"
                    writeFile file: "output/usefulfile.txt", text: "This file is useful, need to archive it."
                    writeFile file: "output/readme.md", text: "readme file"
                    writeFile file: "output/new-file.txt", text: "This is a new file"
                    writeFile file: "output/jibin.txt", text: "This file needs to be excluded"
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
            archiveArtifacts artifacts: 'output/*.txt', excludes: 'output/jibin.txt' onlyIfSuccessful: true
            }
        changed {
        sh 'echo "ERROR in deployment"'
            }
    }
}
