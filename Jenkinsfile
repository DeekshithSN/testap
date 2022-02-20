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
    
    triggers { cron('H */6 * * 3-5') }
    
    options{
    buildDiscarder(logRotator(numToKeepStr: '1')) 
     timeout(time: 1, unit: 'MINUTES') 
    }
    
    stages {
        
        stage('Example') {
            
//             when { equals expected: 2, actual: currentBuild.number }
            when { expression {  params.DEPLOY_ENV == "prod" } }
            input {
                message "Should we continue?"
                ok "Yes, we should."
                submitter "alice,bob"
                parameters {
                    string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
                }
            }
            steps {
                echo "Hello, ${PERSON}, nice to meet you."
            }
        }
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
