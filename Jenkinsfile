pipeline{
  agent any
  stages{
    stage('Build'){
      steps {
        sh 'echo "Hello World"'
        sh '''
          echo "Multiline shell works too"
          ls -lah
        '''
      }
    }
    stage('Upload to AWS'){
      steps{
        withAWS(credentials:'aws-static',region:'us-west-2') {
          s3Upload(file:'index.html', bucket:'aws-static-jenkins-pipeline-bucket', path:'')
        }
      }
    }
  }
}
