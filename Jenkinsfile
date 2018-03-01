node {
    deleteDir ()
        try {
            stage ('clone') {
                checkout scm
            }
            stage ('deploy') {
                sdh "echo 'hello world'"
            }
        }
        catch (err) {
            currentBuild.result = 'FAILED'
        throw err
        }
 }
