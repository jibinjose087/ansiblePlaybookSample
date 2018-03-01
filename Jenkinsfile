node {
    deleteDir ()
        try {
            stage ('clone') {
                checkout scm
            }
            stage ('deploy') {
                sh "ping 197.23.34.56"
            }
        }
        catch (err) {
            currentBuild.result = 'FAILED'
        throw err
        }
 }
