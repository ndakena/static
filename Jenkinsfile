pipeline {
     agent any
     stages {
         stage('Lint HTML') {
              steps {
                  sh 'tidy -q -e *.html'
              }
         }
         stage('Upload to AWS') {
             steps {
                 sh 'echo "Hello AWS"'
                 sh '''
                     echo "Here is multiline shell steps"
                     ls -lah
                 '''
                  withAWS(region:'us-east-1',credentials:'aws-static') {
                  sh 'echo "Using AWS credentials to upload to S3"'
                      s3Upload(pathStyleAccessEnabled: true, payloadSigningEnabled: true, file:'index.html', bucket:'s3ndakena')
                  }
             }
         }
     }
}
