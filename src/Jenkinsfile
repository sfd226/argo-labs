pipeline {

  agent none


  stages{
      stage('Build'){
          agent{
            docker{
              image 'python:alpine3.17'
              args '--user root'
            }
          }
          steps{
            echo 'Compiling vote app'
            sh 'pip install -r requirements.txt'
          }

      }
      stage('Unit Test'){
          agent{
            docker{
              image 'python:alpine3.17'
              args '--user root'
            }
          }
          steps{
            echo 'Running Unit Tests on vote app'
            sh 'pip install -r requirements.txt'
            echo 'Placeholder to run nosetests -v'
          }
      }
      stage('Docker BnP'){
          agent any
          when{
            branch "master"
          }
          steps{
            echo 'Packaging vote app with docker'
            script{
              docker.withRegistry('https://index.docker.io/v1/', 'dockerlogin') {
                  def voteImage = docker.build("xxxxxx/vote:v${env.BUILD_ID}", "./")
                  voteImage.push()
                  voteImage.push("dev")
              }
            }
          }
      }

  }

  post{
    always{
        echo 'Pipeline for vote is complete..'
    }
 
  }

}
