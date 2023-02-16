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
        sh 'git --version'
      }
    }
    stage("Build Image"){
      steps{
        sh 'docker build -t newImage:${BUILD_NUMBER} .'
      }
    }
    stage("Check Image"){
      steps{
        sh 'docker images'
      }
    }
  }
}     
// comment
