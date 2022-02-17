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
               sh 'printenv'
                sleep 120
            }
        }
        
         stage('test') {
          
            
            steps {
               sh 'printenv'
            }
        }

        }
        

}
