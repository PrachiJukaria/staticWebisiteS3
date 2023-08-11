pipeline {
    agent any

    stages{
        stage('deploy to S3'){
            steps{
               sh 'aws s3 cp . s3://statis-file-hosting --recursive'
               sh 'aws s3api put-bucket-policy --bucket statis-file-hosting --policy file://policy.json'
               sh 'aws s3 website s3://statis-file-hosting/ --index-document index.html --error-document error.html'
             
            }
        }
    }
    
}
