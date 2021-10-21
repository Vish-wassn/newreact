pipeline {
    agent any

    stages{
        stage('deploy to S3'){
            steps{
                sh 'aws s3 cp package.json s3://reactapp21oct2021'
                sh 'aws s3api put-object-acl --bucket reactapp21oct2021 --key package.json --acl public-read'
                sh 'aws s3 cp yarn.lock s3://reactapp21oct2021'
                sh 'aws s3api Jenkinsfile --bucket reactapp21oct2021 --key yarn.lock --acl public-read
            }
        }
    }
    post{
        always{
            cleanWs disableDeferredWipeout: true, deleteDirs: true
        }
    }

}
