pipeline {
    agent {
         docker {image 'maven'}
    }

    stages {
        stage('Hello') {
            steps {
               sh 'mvn -version'
            }
            
            post { 
                always { 
            echo 'I will always say Hello again!'
                }
            }

        }
        
        stage('Hello2') {
            steps {
               sh '''
               pwd
               ls -l
               ps -eaf 
               '''
            }
        }    
    }
    post{
        success{
        echo "Job is success"
         cleanWs()
        }
        
        failure{
        echo "job is failed"
        }
        
        always{
            
          cleanWs()
        }
    
    }
    
}
