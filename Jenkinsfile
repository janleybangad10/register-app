pipeline{
    agent {label 'Jenkins-Agent'}
    tools{
        jdk 'Java17'
        maven 'Maven3'

    }
    stages{
        stage("Cleanup Workspace"){
            steps{
                cleanWs()
            }
         }
        stage("Checkout from SMC"){
            steps{
                git branch: 'main', credentialsId: 'github', url: 'https://github.com/janleybangad10/register-app'
            }
        }
        stage("Build Application"){
            steps{
                sh "mvn clean package"
            }
        }

        stage("Test Application"){
            step{
                sh "mvn test"
            }
        }
    }
}