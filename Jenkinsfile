pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
                bat 'mvn clean package'
            }
             post {
                success {
                    echo 'Now Archiving...'
                    archiveArtifacts artifacts: '**/target/*.war'
                }
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
         stage ('Deploy to Staging'){
            steps {
            echo 'Deploying....'
                build job: 'Deploy-to-staging'
            }
        }
        }
   
}