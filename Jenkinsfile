pipeline {
    agent any

    stages{
        stage('deploy to S3'){
            steps{ 
                sh 'aws s3 cp public s3://reactapp21oct2021 --recursive'
                sh 'aws s3api put-object-acl --bucket reactapp21oct2021 --key public --acl public-read'
            }
        }
    }
    post{
        always{
            cleanWs disableDeferredWipeout: true, deleteDirs: true
        }
    }

}
