@Library('libraries')_

pipeline
{
    agent any
    stages
    {
        stage('ContinuousDownload_Master')
        {
            steps
            {
                script
                {
                    cicd.newGit("https://github.com/krishnain/maven.git")
                }
            }
        }
        stage('ContinuousBuild_Master')
        {
            steps
            {
                script
                {
                    cicd.newMaven()
                }
            }
        }
        stage('ContinuousDeploy_Master')
        {
            steps
            {
                script
                {
                  
                    cicd.newDeploy("172.31.81.5","testapp")
                }
            }
        }
        stage('ContinuousTesting_Master')
        {
            steps
            {
                script
                {
                    cicd.newGit("https://github.com/intelliqittrainings/FunctionalTesting.git")
                    cicd.runSelenium("/home/ubuntu/.jenkins/workspace/DeclarativePipeline1")
                }
            }
        }
        stage('ContinuousDelivery_Master')
        {
            steps
            {
                script
                {
                    
                   cicd.newDeploy("172.31.80.42","prodapp")   
                }
            }
        }
        
        
    }
}

