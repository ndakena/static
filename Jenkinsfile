pipeline {
    agent any
    stages {
        stage('Upload to AWS') {
            steps {
                withAWS(credentials: 'aws-credentials', region: 'us-east-1') {
                s3Upload acl: 'Private', bucket: 'ndakenas3', file: 'index.html'
                  }
               }
        }
    }
}
