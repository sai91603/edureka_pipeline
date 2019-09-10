pipeline{
      agent any 
          stages{
              stage('one'){
                  steps{
                  echo 'Hi,this is saicharan'
              }
              }
              stage('two'){
                  steps{
                      input('Do you want to proceed?')
                  }
              }
              stage('three'){
                  when{
                      not{
                          branch "master"
                      }
                  }
                  steps{
                    echo "Hello"
                  }
              }
              stage('Four'){
                  parallel{
                      stage('unit test'){
                          steps{
                              echo "Running the unit test"
                          }
                      }
                      stage('Integration stage'){
                          agent{
                              docker{
                                  reuseNode false
                                  image 'ubuntu'
                              }
                          }
                          steps{
                              echo "Running the integration test"
                          }
                      }
                  }

              }

          }
      
}