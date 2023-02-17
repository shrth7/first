pipeline{
  agent any
  options{
    timestamps()
    timeout(time: 10,unit: 'SECONDS')
    skipDefaultCheckout()
    buildDiscarder(logRotator(numToKeepStr: '10'))
  }
  stages{
    stage("doing parallel"){
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
        sh 'docker build -t my-apache2 .'
      }
    }
    stage("deploy"){
    
      steps{
        retry(3){
          sh 'docker run -dit --name my-running-app3 -p 8080:80 my-apache2'
        }
      }
    }
  }
}     
// comment
