pipeline {
    agent any

    stages{
        stage('deploy to S3'){
            steps{
                sh 'aws s3 cp yarn.json s3://reactapp21oct2021'
                sh 'aws s3api Jenkinsfile --bucket reactapp21oct2021 --key yarn.json --acl public-read
            }
        }
    }
    post{
        always{
            cleanWs disableDeferredWipeout: true, deleteDirs: true
        }
    }

}
