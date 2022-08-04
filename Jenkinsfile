pipeline {
    agent {
        node {
        label "built-in"
        customWorkspace "/media/project"
    }
    }
    stages {
        stage ('building project'){
            steps {
                sh "mvn install"
            }
        }
    }
}
