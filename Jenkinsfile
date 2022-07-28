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
        stage ('deploy to s3 bucket'){
            steps {
                sh "aws s3 cp /media/project/gameoflife-web/target/gameoflife.war s3://28-july-bucket"
            }
        }
        stage ('copy from s3 to slave'){
            agent {
                label "QA"
            }
            steps {
                sh "aws s3 cp s3://28-july-bucket /mnt/server/apache-tomcat-9.0.65/webapps"
            }
        }
    }
}
