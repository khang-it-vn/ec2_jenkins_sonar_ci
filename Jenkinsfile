pipeline{

    agent any

    stages{

        stage('sonar quality check'){
            agent{

                docker{
                    image 'maven'
                }
            }

            steps{

                script{

                    withSonarQubeEnv(credentialsId: 'sonar-token') {
                        
                        sh 'mvn clean install sonar:sonar -Dmaven.repo.local=/var/lib/jenkins/.m2/repository'
                    }
                }
            }
        }
    }
}