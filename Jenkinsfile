@Library('mylibrary')_
pipeline
{
    agent any 
    stages
    {
        stage('ContDownload_master')
        {
            steps
            {
                script
                {
                    cicd.gitDownload("maven")

                }
            }
        }
        stage('ContBuild_master')
        {
            steps
            {
                script
                {
                    cicd.mavenBuild()

                }
            }
        }
        stage('ContDeployment_master')
        {
            steps
            {
                script
                {
                           cicd.DeployTomcat("DeclarativePipelinewithSharedlibraries","172.31.94.45","mytestapp")
   
                }  
            }
        }
        stage('ContTesting_master')
        {
            steps
            {
                script
                {
                     cicd.gitDownload("FunctionalTesting")
                     cicd.RunSelenium("DeclarativePipelinewithSharedlibraries")

                }
            }
        }
        stage('ContDelivery_master')
        {
            steps
            {
                script
                {
                             cicd.DeployTomcat("DeclarativePipelinewithSharedlibraries","172.31.95.78","myprodapp")

                }
            }
        }
    }
}
