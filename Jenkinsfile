pipeline {
    agent {
         docker {image 'maven'}
    }

    environment{
        VERSION = "${env.BUILD_ID}"
    }
    
    options{
    buildDiscarder(logRotator(numToKeepStr: '1')) 
     timeout(time: 1, unit: 'MINUTES') 
    }
    
    stages {
        stage('Hello') {
            
            environment{
               phase1 = "firststage"
              }
            
            steps {
              timeout(time: 30, unit: 'SECONDS') {
                   sleep 35
                }
                                
            }
        }
        
         stage('test') {
          
            
            steps {
               sh 'printenv'
            }
        }

        }
        

}
