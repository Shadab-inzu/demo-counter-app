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
    }
}