pipeline {

agent any

stages{

        stage('Get The code from Git'){
            git 'https://github.com/youssefsiyed/CucmberExample.git'
            }

        stage('Compile and Verify Code'){
            steps {
                bat 'mvn clean verify'
            }
            post {
                success {
                    echo 'Now Archiving...'
                    archiveArtifacts artifacts: '**/target/*.war'
                }
            }
        }

        stage('Report') 
         {
        cucumber fileIncludePattern: '**/*.json', sortingMethod: 'ALPHABETICAL'
         }
        
        }
    }