pipeline {
    agent {
         docker {image 'maven'}
    }

    stages {
        stage('Hello') {
            steps {
               sh 'mvn -version'
            }
        }
        
        stage('Hello2') {
            steps {
               sh '''
               pwd
               ls -l
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
    
    }
    
}
