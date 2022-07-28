pipeline {
    agent {
        {
            label "QA"
        customWorkspace "/media/project"
    }
    }
    stages {
        stage ('building project'){
            steps {
                sh "mvn install"
            }
        }
        stage ('deploy to s3 bucket'){
            steps {
                sh "aws s3 cp /media/project/gameoflife-web/target/gameoflife.war s3://28-july-bucket"
            }
        }
    }
}
