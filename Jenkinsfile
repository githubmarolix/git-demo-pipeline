pipeline{
    agent any
  stages{
      stage('one'){
          steps{
                 echo "hi, this is srinu from rjy "
          }
      }
      stage('two'){
          steps{
                input ('Do you to proceed?')
          }
      }
      stage('three'){
          when{
              not{
                  branch "master"
              }
          }
      }
      steps{
            echo "hello"
      }
  }
      stage('four'){
          parallel{
              stage('unit test'){
                  steps{
                        echo "Running the unit test..."
                  }
              }
              stage('integration test'){
                  agent {
                      docker{
                             reusenode false
                             image 'ubuntu'
                      }
                  }
                  steps{
                        echo 'Running the integration test'
                  }
              }       
          }
}
}
}
}
