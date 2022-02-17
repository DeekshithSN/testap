pipeline {
    agent {
         docker {image 'maven'}
    }

    environment{
        VERSION = "${env.BUILD_ID}"
    }
    
    stages {
        stage('Hello') {
            steps {
               sh 'printenv'
            }
        }

        }
        

}
