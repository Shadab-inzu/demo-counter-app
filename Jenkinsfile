pipeline{
    agent any

    stages{
       
        stage('Git Checkout'){

            steps{
                 git branch: 'main', url: 'https://github.com/Shadab-inzu/demo-counter-app.git'
            }
        }
       stage('Unit Testing'){

            steps{
                  sh 'mvn test'
            }
        }
       stage('Integration testing'){

            steps{
                  sh 'mvn verify -DskipUnitTests'
            }
        }
        stage('Maven Build'){

            steps{
                  sh 'mvn clean install'
            }
        }
        stage('Static Code Analysis'){

            steps{
                script{

                    withSonarQubeEnv(credentialsId: 'sonar-api') {
   
                      sh 'mvn clean package sonar:sonar'
               }
                   
             }
                  
            }
        }


    }
}