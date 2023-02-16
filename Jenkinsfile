pipeline{
  agent any
  options{
    timestamps()
  }
  stages{
    stage("Docker version"){
      steps{
        sh 'docker -V'
      }
    }
    stage("Git Version"){
      steps{
        sh 'git -V'
      }
    }
  }
}     
