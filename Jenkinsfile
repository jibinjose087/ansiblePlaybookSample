node {
    deleteDir ()
        try {
            stage ('clone') {
                checkout scm
            }
            stage ('deploy') {
                sh "echo 'hello world'''"
            }
        }
        catch (err) {
            currentBuild.result = 'FAILED'
        throw err
        }
 }
