pipeline {
    agent any
    stages {
        stage('Upload to AWS') {
            steps {
                sh 'echo "Hellow World"'
                sh '''
                    echo "Multiline shell steps works too"
                    ls -lah
                    '''   
                }
            steps {

                  withAWS(credentials: 'aws-credentials', region: 'us-east-1') {

                       s3Upload acl: 'Private', bucket: 'ndakenas3', file: 'index.html'}
             }
        }
    }
}
