pipeline {
    agent any
        environment {
          VERSION = NEW
        }
            stages {
                stage ('deployment stage'){
                    steps {
                    sh echo "Version number is $VERSION"
                    }
        }
    }
}
