pipeline{
  agent any

  stages{
    stage('Build'){
      steps{
        h 'docker build -t devops-demo .'
      }
    }
    stage('Run'){
      steps{
        sh '''
        docker stop devops-demo || true
        docker rm devops-demo || true
        docker run -d -p 5000:5000 --name devops-demo devops-demo
        '''
      }
    }
  }
}
