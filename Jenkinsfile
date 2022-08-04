pipeline {
    agent {
        node {
        label "QA"
        customWorkspace "/media/project"
    }
    }
    stages {
        stage ('building project'){
            steps {
                sh "rm -rf /media/project/*"
                sh "mvn install"
            }
        }
    }
}
