pipeline {
    agent any
    environment{
        VERSION = "${env.BUILD_ID}"
    }
    
    parameters {
        booleanParam(name: 'DEBUG_BUILD', defaultValue: true, description: '')
        string(name: 'DEPLOY_ENV', defaultValue: 'staging', description: '') 
        choice(name: 'CHOICES', choices: ['one', 'two', 'three'], description: '') 
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
              
                echo "${params.DEBUG_BUILD}"
                echo "${params.DEPLOY_ENV}"
                echo "${params.CHOICES}"
                                
            }
        }
        
         stage('test') {
          
            
            steps {
               sh 'printenv'
            }
        }

        }
        

}
