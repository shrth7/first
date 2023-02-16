pipeline{
  agent any
  options{
    timestamps()
    timeout(time: 10,unit: 'SECONDS')
  }
  stages{
    stage("doing parallel){
          parallel{
            
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
          }
          }
    stage("Build Image"){
      steps{
        sh 'docker build -t newimage:${BUILD_NUMBER} .'
      }
    }
    stage("Check Image"){
    
      steps{
        retry(3){
          sh 'docker images'
        }
      }
    }
  }
}     

