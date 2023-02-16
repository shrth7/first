pipeline{
  agent any
  options{
    timestamps()
  }
  stages{
    stage("Docker version"){
      steps{
        sh 'docker -v'
      }
    }
    stage("Git Version"){
      steps{
        sh 'git -v'
      }
    }
  }
}     
