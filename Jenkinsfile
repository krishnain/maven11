@Library('libraries')_

pipeline
{
    agent any
    stages
    {
        stage('ContinuousDownload_Loans')
        {
            steps
            {
                script
                {
                    cicd.newGit("https://github.com/krishnain/maven11.git")
                }
            }
        }

        stage('ContinuousBuild_Loans')
        {
            steps
            {
                script
                {
                    cicd.newMaven()
                }
            }
        }
        
        
    }
}

