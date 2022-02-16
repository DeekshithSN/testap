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
               ps -eaf
               '''
            }
        }
        
        
    }
}
