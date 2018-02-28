pipeline {
    agent any
        stages {
            stage ('Deploy') {
                steps {
                        timeout(time: 3, unit: 'SECONDS') {
                        input 'Should I start the deployment ?'
                }
            }
        }
    }
}
