pipeline {
    agent any
    stages{
    
    stage('Initialize'){
    steps {
                 echo 'Initialzig ...'
            }
    
     }
         stage('Build'){
            steps {
                sh 'mvn clean package'
            }
            post {
                success {
                    echo 'Now Archiving...'
                    archiveArtifacts artifacts: '**/target/*.war'
                }
            }
        }
    }
}