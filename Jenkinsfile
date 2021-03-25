pipeline {
  agent any
  stages {
    stage("Hello") {
      steps {
        sh 'echo \'Hello Green Team\''
      }
    }
    stage("Upload to AWS") {
      steps {
        withAWS(region:'eu-west-1',credentials:'floreness_credentials') {
          s3Upload(pathStyleAccessEnabled:true, payloadSigningEnabled: true, file:'index.html', acl:'PublicRead', bucket:'yassir-floreness')
        }
      }
    }
  }
}
