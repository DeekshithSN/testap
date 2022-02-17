pipeline {
    agent {
         docker {image 'maven'}
    }

    environment{
        VERSION = "${env.BUILD_ID}"
    }
    
    stages {
        stage('Hello') {
            
            environment{
               phase1 = "firststage"
              }
            
            steps {
               sh 'printenv'
            }
        }
        
         stage('test') {
          
            
            steps {
               sh 'printenv'
            }
        }

        }
        

}
